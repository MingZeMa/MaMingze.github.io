---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Lane-Line
title: Lane Line Tracking

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Ma Mingze
# multiple category is not supported
category: 718-Smart-Car
# multiple tag entries are possible
tags: [Robotics, Semantic Segmentation]
# thumbnail image for post
img: ":Lane_logo(vertical).png"
# disable comments on this page
#comments_disable: true

# publish date
date: 2021-7-15 08:11:06 +0900

# seo
# if not specified, date will be used.
#meta_modify_date: 2022-02-10 08:11:06 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# please use the "image_viewer_on" below to enable image viewer for individual pages or posts (_posts/ or [language]/_posts folders).
# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in _data/conf/main.yml.
#image_viewer_on: true
# please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (_posts/ or [language]/_posts folders).
# image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in _data/conf/main.yml.
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---





<div align='center'>
    <img src="/assets/img/posts/Lane-Logo.png">
</div>

***


# Project Introduction

<!-- outline-start -->This is a Lane line tracking algorithm for multifunctional smart logistics trolleys based on Jetson nano<!-- outline-end -->, which needs to have various functions including LIDAR map navigation, obstacle avoidance, shortest path planning, and traffic light and lane line recognition. In this project, I realized the UNet-based lane line recognition, and used the coordinates of the points on the lane line for curve fitting, combined with the horizontal offset of the cart from the lane line, to calculate the turning angle needed by the cart so as to realize the cart's automatic tracking along the lane line. The algorithm finally realizes the stable recognition of the lane line under different lighting conditions and the trajectory at a speed of 1m/s.
<a name="7960fa1a"></a>
# Project WorkFlow

## Lane Line Recognition

Two schemes are used for the lane line recognition part, one is a scheme that uses **UNet** to implement semantic segmentation of lane lines, and the other is a scheme that uses **normal image processing algorithms** and uses **sliding window** detection to implement it.
<a name="DMcQO"></a>
### Multi-Feature Fusion Lane Line Recognition :

- Multi-Feature Fusion
   -  Sobel X 
   -  Gradient information of the X and Y directions 
   -  Gradient direction 
   -  Information of L channel and S channel in HLS space 

<div align='center'>
    <img src="/assets/img/posts/Lane-Effect1.png">
</div>

-  Slide the window to extract the lane line centerline 
   - Setting window parameters and sliding range
   - Setting the sliding starting point
   - Sliding according to the recognized pixel value in the window

<div align='center'>
    <img src="/assets/img/posts/Lane-Effect2.png" style="width:75%;">
</div>

<a name="CTvdz"></a>
### Semantic segmentation based on UNet :

-  Label and train using labelme 
-  Further improve the robustness of the model 
-  Simplify the steps of repeated parameter setting, which automatics the debugging process.

<div align='center'>
    <img src="/assets/img/posts/Lane-Effect3.png">
</div>

<a name="zw8SV"></a>
## Lane Line Tracking

- Use curve fitting to get an expression for the lane lines.
- Obtaining the slope of the lane line and calculating the turn angle of the cart by combining it with the cart's offset from the center.
- Communicate with the host computer to realize control

**The complete process of vehicle tracking is as follows:**

<div align='center'>
    <img src="/assets/img/posts/Lane-EffectFlow.png">
</div>

#  Project Performance
<a name="g38Hk"></a>

## Lane line tracking section

<iframe width="560" height="315" src="https://www.youtube.com/embed/GRdpbkkbAx4" frameborder="0" allowfullscreen></iframe>

<a name="cqQ96"></a>

## Vehicle full functionality implementation
<iframe width="560" height="315" src="https://www.youtube.com/embed/GlH-n75vsQE?si=fBwX3iDP6uo6MbVd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>