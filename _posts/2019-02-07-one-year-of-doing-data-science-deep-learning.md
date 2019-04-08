---
title: One Year of Doing Data Science & Deep Learning
category: Data Science
feature_text: |
  One Year of Doing Data Science & Deep Learning
feature_image: "/images/floppy.jpg"
comments: true
---

For the past year, I have been doing data science (DS) & deep learning (DL) to understand drug bioactivation, toxicity and their implications on drug-induced liver injuries (DILI). I come from a background of molecular modeling which is a computational approach to analyse molecules, but I would not consider it to be DS or  DL. Since, DS and DL were a new subject that I picked up to master, this blog post is an account of my year-long journey. 

During my wait for the VISA to be sanctioned for my current position I asked my employer if there is anything that I should learn that would help me to get a good start in deep learning. The answer was Keras or Tensorflow that runs on Python. Ok, so I learned rudimentary Keras and Tensorflow and built intermediate level expertise in Python programming language. However, if someone wants to learn DL and if all he knows is vanilla Python programming then probably Keras or Tensorflow is not the first place to start. Most of the time in a DL project is spent in data wrangling which means getting the input data in the right format to be represented to a DL algorithm and re-formating the DL output for inference. 

Therefore, in my opinion, an excellent place to start is to learn how to use data handling and manipulation libraries such as Numpy and Pandas. These are the two most crucial tools that you would use in any DL project. Next, learning Matplotlib would help you to plot graphs for your input data and results. You can always use a code editor to practice these tools, but nothing beats Jupyter notebook. In Jupyter you can write markdown notes as you learn, execute small snippets of code in individual cells and also plot graphs in the same space. It is suitable for trying and testing code especially during the data wrangling stage as it allows you to visualize Numpy and Pandas data frames effectively as you go.

Once you have mastered Numpy, Pandas, and Matplotlib familiarizing yourself with Scipy and Scikit-Learn is highly recommended. They are two general purpose data science and machine learning libraries that come very handy for various purposes during a DL project. I use them more often than Keras or Tensorflow. Some of the uses are for data scaling, creating train-test splits, generating stratified folds for cross-validations, metrics like ROC-AUC, MSE, MAE, etc., feature selection, statistical tests amongst others. 

In my opinion, these are the bare minimum tools you need to facilitate your DL project in addition to the main DL libraries such as Keras or Tensorflow. If you want to add a few extra feathers in your cap, I can recommend learning Seaborn and Plotly for graphs and plots. They are based on Matplotlib, but with enhanced features.  Pyarrow Parquet a library that can take advantage of Parquet format for columnar data storage. On occasions, I have also used Stats Model library for some conventional statistical procedures. 

Now, coming to Keras and Tensorflow people usually start with Keras which is a higher level abstraction API for several DL engines including Tensorflow because of its ease. However, learning Tensorflow itself has a lot of incentives. Tensorflow gives you a lot more control over what you can do with your DL algorithm. Keras is undoubtedly the right place to start and is also very good for prototyping and also very suitable for many projects that can be solved using off the shelf DL procedures. However, if you are picking up DL for a long run, then Tensorflow would be inevitable. 

If you are a person like me who has come from a non-programming background, then you would also like to learn some additional tools that are part of any professional programmer's toolbox. Probably nothing is more important than a version control system (VCS). At the moment I guess the two most widely used VCSs are Git and Mercurial. They both can be installed on your local machine or can be used in the cloud. Bitbucket supports both Git and Mercurial repositories, and GitHub supports git. Having a GitHub profile is not only good for keeping track of your programmes, but they also serve as a code portfolio that you can showcase during a job interview, etc. At this point, I should even mention my favorite code editor that is Microsoft Visual Studio Code. It's free, cross-platform, officially supports Python and GitHub integration.

The last piece of advice DL is only as useful as your domain knowledge in the subject that you are trying to study. DL is not going to magically find out answers for you if you are not asking the right question and providing it the correct data to look into.

Top Banner Photo by 
<a style="background-color:black;color:white;text-decoration:none;padding:4px 6px;font-family:-apple-system, BlinkMacSystemFont, &quot;San Francisco&quot;, &quot;Helvetica Neue&quot;, Helvetica, Ubuntu, Roboto, Noto, &quot;Segoe UI&quot;, Arial, sans-serif;font-size:12px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px" href="https://unsplash.com/@thefredyjacob?utm_medium=referral&amp;utm_campaign=photographer-credit&amp;utm_content=creditBadge" target="_blank" rel="noopener noreferrer" title="Download free do whatever you want high-resolution photos from Fredy Jacob"><span style="display:inline-block;padding:2px 3px"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-2px;fill:white" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M10 9V0h12v9H10zm12 5h10v18H0V14h10v9h12v-9z"></path></svg></span><span style="display:inline-block;padding:2px 3px">Fredy Jacob</span></a> on Unsplash