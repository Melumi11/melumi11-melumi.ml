---
layout: post
title: "3D Printing 2D Images: Guide to Lithophanes"
date: 2023-12-09 11:59:00-0400
description: Step by step guide to printing your own lithophanes
tags: 3D-printing
categories: 3D-printing
giscus_comments: true
related_posts: false
thumbnail: assets/img/lithophane/thumbnail.jpg
toc:
  beginning: true
---

### Introduction

[Jump to checklist](#the-checklist)

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lithophane/ttm_frontlit.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lithophane/ttm_backlit.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lithophane/ttm_original.avif" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    To the Moon lithophane lit from the front and back. Original art by Freebird Games
</div>

## Intro:

A lithophane is a thin plaque of translucent material which has been molded to varying thickness, such that when lit from behind, the different thicknesses show as different shades, forming an image.

3D printed lithophanes are a cool and easy way to display your favorite images. They make for  unique gifts and fun decorations. Any image that looks good in black & white can be used, which makes it perfect for photos and posters.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lithophane/sdv_frontlit.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lithophane/sdv_backlit.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lithophane/sdv_original.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Stardew Valley lithophane lit from the front and back. Original art by ConcernedApe
</div>

### Pre-reqs:

* Know how to operate a 3D printer (or have someone who does)
* Choose an image that looks good in black & white
* White filament

### This guide will teach:

* How to turn an image file into a .stl file
* What slicer settings to use when slicing the .stl file into a .gcode file

<br>

## Guide:

### Making your file

First, choose an image that looks good in black & white.

There are a few lithophane model generators online. I use https://3dp.rocks/lithophane/

* Upload your image under "Images"
* Choose "Outer Curve" under model. Do not choose "Flat"! We can make it flat in settings. (Imagine outer curve as a section of a lampshade where the lamp is the light source. I don't suggest choosing "Flat" because the lithophane must be printed standing up.)

Under "Settings" -> "Image Settings":
* Choose "Positive Image" (important) (this is for the lighting from behind effect)

Under "Settings" -> "Model Settings":
* Max size: choose somewhere between 100 and 200 (200 is huge imo)
* Thickness 3mm (impacts how much light needed)
* Border: 4mm (up to you, none if you want no border)
* **If you don’t want curve**: set curve to 1. Go to Model for a 3d preview.

### Slicer setup:

**We must print the lithophane standing up.**

> Printing it standing up means that there are more shades of gray the printer can print, resulting in a higher quality image. This is because printers have higher resolution/quality in the x/y direction than z (up-down). If this doesn't make sense, try slicing it both ways and comparing the preview. If you can do it better, I would love to be proven wrong.

* In your slicer, set the quality to a high quality (like 0.15mm layer height or less). Besides what I list below, default settings should be fine.
* Set the infill to 100%. Setting it lower won't change anything anyways, as it is so thin that there is no space for infill.
* Make sure a brim (or raft) is added so it doesn't fall while printing. Adhesion is important, as this is a thin and tall model. Mine has fallen over before in a ~12-hour long print. This mostly affects non-curved lithophanes.
* No need to add supports. Any overhangs are tiny enough to not matter.

Make sure the print does not fall over if you don't make it curved, and assert that the bed is level.

<div class="row mt-3" style="width: 50%; margin: 0 auto">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lithophane/ttm_printing.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    This To the Moon lithophane was printed standing on the short edge, but I have also printed one standing on the long edge and I can't tell if there's a quality difference.
</div>

Remember that print failures are to be expected, and it will likely take a number of tries to get a clean print (this one took me four tries). I did most of my research for this project by searching on google and reading forums + watching youtube videos.

<br>

## The Checklist

<ul>
    <li>
        <input type="checkbox" id="1">
        <label for="1">Get white filament and black & white image</label>
    </li>
    <li>Go to <a href="https://3dp.rocks/lithophane/">https://3dp.rocks/lithophane/</a></li>
</ul>

Under "Images"

* <input type="checkbox" id="2">
    <label for="2">Upload Image</label>

Under "Model"

* <input type="checkbox" id="3">
    <label for="3">Select "Outer Curve"</label>

Under "Settings" -> "Image Settings":
* <input type="checkbox" id="4">
    <label for="4">Select "Positive Image"</label>

Under "Settings" -> "Model Settings"
<ul>
    <li>
        <input type="checkbox" id="5">
        <label for="5">"Maximum Size": 100 - 200 (200 is huge imo)</label>
    </li>
    <li>
        <input type="checkbox" id="6">
        <label for="6">"Thickness": 3mm</label>
    </li>
    <li>
        <input type="checkbox" id="7">
        <label for="7">"Border": 4mm (optional)</label>
    </li>
    <li>
        <input type="checkbox" id="8">
        <label for="8">"Curve": 1 (optional)</label>
    </li>
</ul>

<input type="checkbox" id="9">
    <label for="9">Preview and download under "Model"</label>

#### Slicer: 

<ul>
    <li>
        <input type="checkbox" id="10">
        <label for="10">Set quality to high quality (like 0.15mm layer height or less)</label>
    </li>
    <li>
        <input type="checkbox" id="11">
        <label for="11">Set infill to 100%</label>
    </li>
    <li>
        <input type="checkbox" id="12">
        <label for="12">Add brim/raft</label>
    </li>
    <li>
        <input type="checkbox" id="13">
        <label for="13">Make sure the model is standing up and supports are off</label>
    </li>
</ul>

Now just print and make sure the first few layers are good!

<br>

Thanks for reading my post. Please leave a comment or reach out if you have any questions :)