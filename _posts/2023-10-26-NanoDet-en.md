---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_NanoDet
title: ArmorDetection Based on NanoDet

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Ma Mingze
# multiple category is not supported
category: RoboMaster
# multiple tag entries are possible
tags: [Robotics, Object Detection]
# thumbnail image for post
img: ":NanoDet-Logo(vertical).png"
# disable comments on this page
#comments_disable: true

# publish date
date: 2023-6-9 08:11:06 +0900

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
    <img src="/assets/img/posts/NanoDet-Header.jpg">
</div>


---

**<center>NanoDet-based Four-Point Armor Detection</center>**

- 🚩**End-to-end:** end-to-end direct output of the four corner points of the armor.
- ⚡**High speed:** can reach 80+ FPS.
- 🏆**Easy Deployment:** Rapid Model Deployment with OpenVINO.

---

<a name="PE0vg"></a>
# Project Introduction
<!-- outline-start -->This is a four-points Armor plate recognition algorithm for RoboMaster based on NanoDet. <!-- outline-end -->In the RoboMaster Robot Self-Aiming System Recognition section we also tried an end-to-end object detection scheme. Due to the need to calculate the distance between the enemy robot and our robot, we have to get the four corner points of the enemy robot's armor, the traditional object detection algorithms get the upper-left corner points of the rectangular box as well as the length and width of the box, so that the output will always be a positive rectangle, but our armor may be tilted in the field of play, so we modified the loss function of the traditional object detection and the detection head, changing the final output directly to the four corner points of the quadrilateral, which greatly improves the operational efficiency of the recognition network. This project is based on the modification on NanoDet-plus, and we are very grateful to the authors for the open source!
<a name="DTIQd"></a>
# Project WorkFlow
**The overall flow of the project is as follows:**
<div align='center'>
    <img src="/assets/img/posts/NanoDet-Flow.png" style="width:150%;">
</div>

Our project makes changes **based on NanoDet-Plus**, the main parts changed are the loss function during training and the detection head of the network.

**The backbone is a lightweight ShuffleNetV2**, which can greatly improve the speed of the network while guaranteeing the recognition stability. In the feature fusion part, we directly adopt the method provided by the authors, and use the lightweight and high-performance **GhostPAN**.The detection head part finally has **three scales of detection head** outputs, and each scale uses the same set of convolutions for edge regression and classification, and finally splits them into two parts, and based on the task we want to achieve, we keep the classification part of the original detection head, and change the original four outputs to the corresponding regression part. The original four outputs are changed to eight outputs corresponding to the coordinates of the four points of the rectangle.

In the training part, we also use the training assistance module Assign Guidance Module (AGM) provided by the authors together with the Dynamic Soft Label Assigner (DSLA) to solve the optimal label matching problem in the lightweight model. This module is only used during the training process and discarded directly after training without affecting the speed of the network. The original authors used classification loss, IoU loss, and dis loss in the loss function part, but due to the specificity of our detection task, the IoU calculation of the rotated rectangle is very complicated, and because the regression of the four corner points needs to consider whether the generated polygon is convex or concave polygon, the IoU loss is very difficult to converge, so we delete this part, and we also change the original dis Loss to L1 Loss to regress the coordinates of the corner points.
<a name="ONsDl"></a>
# Project Performance
Based on our own photographed and labeled armor dataset for testing, the model accuracy is as follows:

| **Average accuracy of classification** | **Armor recognition Precision** | **Armor Recognition Recall** |
| :---: | :---: | :---: |
| 0.93 | 0.932 | 0.917 |
{:data-align="center"}


The inference speeds deployed on Intel's NUC platform after OpenVINO optimization are as follows:

| **computing platform** | **Whether int8 quantization** | **FPS** | **Throughout Time(ms)** |
| :---: | :---: | :---: | :---: |
| Inter CPU | No | 62.5 | 16 |
| Inter CPU | Yes | 83.3 | 12 |
{:data-align="center"}


