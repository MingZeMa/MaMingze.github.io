---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_RuneDetection
title: RuneDetection

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Ma Mingze
# multiple category is not supported
category: RoboMaster
# multiple tag entries are possible
tags: [Robotics, Key Point Detection]
# thumbnail image for post
img: ":Rune(vertical).png"
# disable comments on this page
#comments_disable: true

# publish date
date: 2023-7-31 08:11:06 +0900

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
    <img src="/assets/img/posts/RuneDetection.png">
</div>

---

**<center> Key-Points Detection of Power Rune for RoboMaster</center>** 

- 😎**TopDown structure:** Key-Points detection based on YOLOX and RTMPose.
- ⚡**Extremely high speed:** 6ms for object detection part, 1.8ms for points detection part.
- 🌈**Easy to Deploy:** Use OpenVINO for Deployment.

---

<a name="qNNEf"></a>
# Project Introduction
<!-- outline-start -->A Key point detection algorithm for RoboMaster Power Rune Detection. Implemented with YOLOX and RTMPose. A speed of 12ms per frame can be achieved.<!-- outline-end --> In the RoboMaster competition, we need to accurately hit five rotating fan blades from 8m away, and in this process, we need to design a highly robust recognizer to obtain the coordinates of the four corner points of the fan blades as well as the category of the fan blades. In this project, I mainly used YOLOX and RTM-Pose to realize the Top-Down key point detection algorithm for fan blades. At the same time, I also replaced the original Backbone of YOLOX with ShuffleNetv2, which has a smaller number of parameters, and deployed the model on a MiniPC using OpenVINO, which increased the running speed of the model by 50% through int8 quantization, and dramatically improved the speed of recognizing energy organs. In the end, the project can complete the identification of all the fan blades of the energy organs within 12ms.
<a name="JF6WQ"></a>

# Project Introduction

**The project flow is shown below:**
<div align='center'>
    <img src="/assets/img/posts/RuneDetection-Flow.png">
</div>

The overall structure of the project adopts Top-Down keypoint detection. First of all, we need to get the position of the Bounding Box of each fan blade and the category of the corresponding fan blade, which is a very important part of the subsequent hitting logic, and this stage is realized by using YOLOX, the Anchor Free structure greatly improves the running speed of the network, and we further improve the running speed of the network by modifying the network's Backbone. After obtaining the Bounding Box of the fan blades, we input the corresponding ROIs into the keypoint detection network, which is realized by using RTMPose, whose special structure can also bring the simultaneous improvement of speed and accuracy.
<a name="PCSYf"></a>
# Project Performance
<a name="eWgy8"></a>

## Project running speed

| **computing platform** | **Whether int8 quantization** | **YOLOX** | **RTMPose** | **Total time(5 blades)** | **Frame rate(5 blades)** |
| :---: | :---: | :---: | :---: | :---: | :---: |
| Inter CPU | No | 16ms | 5ms | 41ms | 24.3 FPS |
| Inter CPU | Yes | 5ms | 1.8ms | 14ms | 71.4 FPS |
{:data-align="center"}

<a name="UNzMp"></a>
## Project Recognition Effect
**Red Power Rune Recognization Effect**
<iframe width="560" height="315" src="https://www.youtube.com/embed/sY38wjgPDRs?si=t-KgGF4T5lOxt9Q1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

**Blue Power Rune Recognization Effect**
<iframe width="560" height="315" src="https://www.youtube.com/embed/aXhx7m5x6GM?si=et5qTe3wlf2EiNC-" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
<a name="g4u24"></a>

## Power Rune Strike Effect
<iframe width="560" height="315" src="https://www.youtube.com/embed/msPsvtc1Gms?si=UjqTMwYN83ki9Z0v" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>