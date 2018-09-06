---
title: Using Inkscape for chemical structure/pathway drawing
category: HowTo
feature_text: |
  Using Inkscape for chemical structure/pathway drawing
feature_image: "/images/dictionary.jpg"
comments: true
---

Inkscape is a versatile vector drawing cross-platform free software which can be used for various types of complex drawings ranging from designing adverts to scientific drawings. I mostly use it for drawings related to biology, specially biosynthesis pathways. Drawing a biosynthesis pathway usually require a bunch of arbitrary symbols such as spheres and a number of chemical moieties attached to them, along with arrows in different directions. There are many freely available software available for drawing standard chemical structure but firstly most of that software are for windows which is a problem for Linux users and secondly, they are not very good for drawing different shapes and arrows associated with the chemical structure.

One of the expedient ways of dealing with this issue which many people do is to draw a portion of the chemical entity in a structure drawing software then export it to a bitmap. Then pull the bitmap in a generic drawing software and do the rest. The other crude, time taking and not so accurate way is to draw the whole thing in a generic drawing software. The problem with the first method is if you export the structure to a bitmap then you can not extend it further, it is fixed for its resolution, any attempt to resize the image will result in distortion. The second method is time taking as you will have to draw the bond lengths and angles very carefully for each and every bond and angle type so that they do not look irregular. And drawing bonds in wedge-dash notation is also not very easy with a standard drawing software.

Both the above-mentioned problems can be taken care of by using a chemical drawing package which can export the chemical drawing in a vector format such as SVG. This SVG file, unlike a bitmap, can be stretched to any size without any distortion and because the structure is drawn by a chemical drawing software the bond length, angle and proper naming in already taken care off.

For this purpose, I personally use and recommend [Marvin Sketch](https://chemaxon.com/products/marvin) in combination with Inkscape. Marvin Sketch is a cross-platform free software which is easy to use and can export the structure file in various formats including SVG. This SVG file can then be imported into Inkscape and further modified like any other vector graphics. Below is an example of a biosynthesis pathway I created recently for my thesis.

![Pathway](/images/pathway.png)