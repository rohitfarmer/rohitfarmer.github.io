---
title: Cloud Convert to convert PostScript into SVG format
category: HowTo
feature_text: |
  Cloud Convert to convert PostScript into SVG format
feature_image: "/images/clouds.jpg"
comments: true
---

Yesterday I discovered a really cool website [Cloud Convert](https://cloudconvert.com/) for converting different document file formats for example from PostScript to SVG. I use much software in my research which generates output in PostScript format. Postscripts are editable using a text editor if you know how the PostScript language works. I find it easier to work with the SVG format in Inkscape. So I was working with a software called LigPlot which maps the amino acids interacting with the bound ligand and present them as the residues forming hydrogen bonds or the hydrophobic interaction. LigPlot gives the output in PostScript format, it does have many options to control the output but in my case, I wanted to create a grid of several outputs and present them as one figure. Previously I just used to pull the .ps files into Gimp and convert them to PNG for further processing. But converting .ps into .png losses its quality and there are only a few things you can do with it. However, converting a .ps into .svg file gives you more control over the image and as both the formats are vector graphics the result is very sharp without any quality loss. I used Cloud Convert to convert the .ps files into .svg and then used Inkscape to do the editing which I wanted to do, made the grid of the different images and then exported it to .pdf. The reason I exported it to .pdf because I am using Latex for my PhD thesis and it works well with .pdf files. Therefore, if I have a graph or a line drawing I would have them as .pdf because not only they are all vector images but also very small in size as compared to .png or .jpeg.