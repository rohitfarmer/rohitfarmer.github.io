---
title: How to use docker to run multiple neo4j servers simultaneously
category: HowTo
feature_image: "/images/neo4j.jpg"
comments: true
---

Neo4J graph database server can only mount one database at a time. To run more than one instances of the neo4j server with different databases mounted on them one of the efficient methods is to use [neo4j docker image](https://hub.docker.com/_/neo4j/). The key to using more than one neo4j servers simultaneously is to use different ports for http, https and bolt connections which is relatively easy to do with the docker image. For my purpose, I also had to configure neo4j in such a way that it can access the database from a non-default location.

**Step 1: Installing the neo4j docker image.**  
Presuming that you already have docker installed and also that you are working in Linux environment:

    docker pull neo4j

**Step 2: Running neo4j docker image.**  
By default, the neo4j docker image mounts the following folders:  

    home:         /var/lib/neo4j
    config:       /var/lib/neo4j/conf
    logs:         /var/lib/neo4j/logs
    plugins:      /var/lib/neo4j/plugins
    import:       /import
    data:         /var/lib/neo4j/data
    certificates: /var/lib/neo4j/certificates
    run:          /var/lib/neo4j/run

These directories may correspond to the already existing directories on your system. In my case, I already had a neo4j community server running on my machine so all these locations were there and were being used by the server. Therefore, I had to provide a custom location that would provide the same information. These locations would not be there in your computer if you have not installed the server version and only intending to use the docker image. To my knowledge the most import of the above-mentioned folders are data this is where your actual database will be created/stored, import to put for example CSV files for import, conf to put neo4j.conf file. 

The command below is going to run the neo4j docker image taking care of running the server on non-default ports and also creating or mounting the required folders from the desired location. 

    docker run --detach --name=my-neo4j --rm --env=NEO4J_AUTH=none \
    --publish=7475:7474 --publish=7476:7473 --publish=7688:7687 \
    --volume=$HOME/neo4j/data:/data \
    --volume=$HOME/neo4j/import:/import \
    --volume=$HOME/neo4j/conf:/conf \
    neo4j

*Breaking down the above-mentioned command.*

docker run ...... neo4j is to run the neo4j docker image.  
--detach to run the container in the background and return the prompt.   
--name=my-neo4j to give the desired name to the docker instance otherwise docker will choose a random name which might not be very easy to remember if we want to refer to this session in future for some reason.   
--rm is to delete the docker instance from the list upon session termination. This is useful if we want to reuse the same name.   
--env=NEO4J_AUTH=none to set up the environment for no password login to the neo4j database.   
--publish=7475:7474 --publish=7476:7473 --publish=7688:7687 to publish/forward the default http, https and bolt ports to the desired ports. In this case, the http, https and bolt ports will be forwarded to the desired 7475, 7476 and 7687 respectively.  
--volume=$HOME/neo4j/data:/data \  
--volume=$HOME/neo4j/import:/import \  
--volume=$HOME/neo4j/conf:/conf \  
to mount the desired locations for the database creation or access. 

*Note: If you are running this command for the first time, it will create the folders mentioned in --volume tag. Otherwise, it will mount the existing folders to the neo4j docker defaults.*  

If no error is returned then your neo4j server is running and should have been mapped to the desired ports and folders.

**Step 3. Check the docker and neo4j server running status.**  
To check the current running docker session(s).

    docker ps

This should give you an output something like this:  
    CONTAINER ID  IMAGE   COMMAND                  CREATED          STATUS         PORTS                                                      NAMES
    1afa157d9caa  neo4j   "/sbin/tini -g -- ..."   36 minutes ago   Up 36 minutes  7473/tcp, 0.0.0.0:7475->7474/tcp, 0.0.0.0:7688->7687/tcp   my-neo4j

To terminate this session:  

    docker kill my-neo4j

To check neo4j running status: open a web browser and then navigate to  

http://localhost:7475 (or the port that you have used for forwarding in step 2)

It should render you a page like the one below:

![Neo4j Login Page](/images/neo4j-1.png)

Change the bolt port to 7688 (or the port that you have used for forwarding in step 2), leave the password field empty (as we have asked for no authentication in step 2) and click connect.

It should connect you to your default graph.db database which should look something like below.

![Neo4j Connection Established](/images/neo4j-2.png)


