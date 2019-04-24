---
title: How-to run Jupyter notebook in an interactive node on a High-Performance Computer (HPC).
category: HowTo
feature_text: |
  How-to run Jupyter notebook in an interactive node on a High-Performance Computer (HPC).
feature_image: "/images/computer.jpg"
comments: true
---

Below is an example protocol to run Jupyter notebook in an interactive node on a high-performance computer (HPCs). Most of the HPCs have their specialised way of interacting with them. Therefore, you may have to tweak this protocol as per your need. I would be happy to discuss and troubleshoot with you; contact me at [rohit.farmer@gmail.com](mailto:rohit.farmer@gmail.com). Any suggestions to augment this protocol with more advanced features are welcomed.

1. SSH to the HPC.    
2. Claim an interactive node (follow the standard procedure for your HPC, in my case it is `qrsh`).   
3. Note the interactive node name.  
4. Run Jupyter on the claimed interactive node by `jupyter notebook --no-browser --ip='0.0.0.0'` or create an alias in your bashrc for a shortcut. For example `alias jup='jupyter notebook --no-browser --ip='0.0.0.0''`.  
5. On your computer start another SSH session with tunnelling using the interactive node name as noted above `ssh user@host -L8888:nodeName:8888 -N`. *The prompt probably won't return and you may also not see any message in your terminal, but as long as there is no error message, it's probably running fine.*  
6. To avoid re-writing the code in step 5 every time you tunnel you can use the shell script below.  

I named it `jupssh`.  
```
#!/bin/sh

# Check if the arugment is passed.
if [[ $# -eq 0 ]];
then
    echo 'Usage: jupssh <node name>'
    exit 1
fi

ssh user@host -L8888:$1:8888 -N
```

* Copy the URL that the Jupyter daemon has generated in step 4 and paste it in the browser on your computer. URL should look something similar to `http://(nodeName or 127.0.0.1):8888/?token=3f7c3a8949b3fa1961c63653873fea075a93a29bffe373b5`. Choose either nodeName or 127.0.0.1 in the URL.

Top banner photo by 
<a style="background-color:black;color:white;text-decoration:none;padding:4px 6px;font-family:-apple-system, BlinkMacSystemFont, &quot;San Francisco&quot;, &quot;Helvetica Neue&quot;, Helvetica, Ubuntu, Roboto, Noto, &quot;Segoe UI&quot;, Arial, sans-serif;font-size:12px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px" href="https://unsplash.com/@fedechanw?utm_medium=referral&amp;utm_campaign=photographer-credit&amp;utm_content=creditBadge" target="_blank" rel="noopener noreferrer" title="Download free do whatever you want high-resolution photos from Federica Galli"><span style="display:inline-block;padding:2px 3px"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-2px;fill:white" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M10 9V0h12v9H10zm12 5h10v18H0V14h10v9h12v-9z"></path></svg></span><span style="display:inline-block;padding:2px 3px">Federica Galli</span></a>