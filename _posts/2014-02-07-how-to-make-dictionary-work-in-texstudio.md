---
title: How to make dictionary work in TexStudio
category: HowTo
feature_text: |
  How to make dictionary work in TexStudio
feature_image: "/images/dictionary.jpg"
comments: true
---

I recently started using LaTex for my PhD thesis. I would say it takes a while to get your head around it but once it works it’s a fun thing to do. And it is so much easy to work with large documents such as a thesis than using MS Word or LibreOffice Writer. I am using TexStudio as my LaTex IDE and honestly speaking I find it better than others available for the same purpose. One of the advantages is that you can use a dictionary for spell checking and in contrast to TexMaker (which is the main source code on which the TexStudio is built) you can also add words in the dictionary. I use my office computer as well as my laptop to write my thesis and I wanted that if I add a word in TexStudio dictionary on my office computer it should also get added to the TexStudio dictionary on my laptop. I figured out that the best way to do this is if I can make the same dictionary access to both the computers. So I used Dropbox to store the dictionary files. TexStudio can work with the OpenOffice dictionaries. So here are the steps that I followed to make the dictionary work in TexStudio.

Step 1: Download the OpenOffice dictionary (http://extensions.openoffice.org/en/project/english-dictionaries-apache-openoffice). The downloaded file will be a .oxt archive, which can be opened using any archive manager. Extract the en_GB.aff and en_GB.dic files (this is dictionary for British English).

Step 2: Create a folder in Dropbox say dictionary and move the extracted .aff and .dic files to this folder.

Step 3: Open TexStudio and click on the menu Options > Configure TexStudio.

Step 4: On the General tab look for the section Dictionaries. And give the path to the dictionary in the Dropbox folder. It will automatically show the dictionaries available in that folder for you to choose. And you are done.

![Configure TexStudio](/images/ConfigureTexStudio.png)

**Note:** The OpenOffice dictionaries actually do not add the word in the main dictionary file but instead it creates another file with the extension .ign. This file contains the list of the words which user has either added or ignored during the spell check. To add a word to the dictionary you have to right-click on the word and choose to ignore always. This will add the word in the ignore list and next time when you will open the document that ignored word will not be marked as a spelling mistake. The advantage of putting the dictionary in the Dropbox folder is that when you ignore a word using one computer it will also be updated on the other computer, hence the same dictionary and ignore list can be used on multiple computers.