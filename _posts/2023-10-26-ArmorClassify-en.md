---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_ArmorClassify
title: ArmorDetection Based on CNN

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Ma Mingze
# multiple category is not supported
category: RoboMaster
# multiple tag entries are possible
tags: [Robotics, Classification]
# thumbnail image for post
img: ":ArmorClassify-Logo(vertical).png"
# disable comments on this page
#comments_disable: true

# publish date
date: 2022-4-15 08:11:06 +0900

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



# <center>Armor  detection algorithm based on OpenCV and CNN</center>

***

**<center>Two-stage Armor Detection program for the RoboMaster</center>**

- **📚Unique architecture:** using a traditional algorithm to extract armors' features and then using an armor classifier to get classification of armors.
- **⚡️High Efficiency:** Compact network architecture with a streamlined framework that can achieve **150+ FPS**.
- **🔝High accuracy:** **97% precision** and **98% recall** can be achieved.

***

<a name="Yq3lC"></a>
# Project Introduction
<!-- outline-start -->Armor plate recognition algorithm based on OpenCV and CNN. The algorithm can reach 97% precision, 98% recall and 150+FPS.<!-- outline-end --> This project is mainly used in RoboMaster, a national college robotics competition, where self-aiming of enemy robots is required. The traditional algorithm of self-aiming requires the use of traditional image processing algorithms and armors classifier to achieve the recognition and classification of enemy armors. 
<a name="U2coo"></a>
# Project WorkFlow
**The overall flow of the project is shown in the figure below:**<br />
<div align='center'>
    <img src="/assets/img/posts/ArmorClassify-Flow.png" style="width:150%;">
</div>
<br />The overall project can be divided into 6 steps. Firstly the image to be detected needs to be acquired, in the competition we use an industrial camera for image acquisition. In the second step we need to binarize the image for the subsequent detection process. The third step is to find the contours in the binarized image and filter the contours to get all the possible light bars in the image. The fourth step is to match all possible light bars by setting certain matching conditions, screening out the light bars that fail to match or the armor plate parameters obtained after matching do not meet the conditions at all, and obtaining all possible armors regions in the image. The fifth step inputs the ROIs of all possible regions of the armor into the CNN for classification to get the categories, and filters out the incorrect armors that are classified as negative samples. The sixth step gives the coordinates of all the correct armors in the figure along with their categories.

<a name="z0dwO"></a>
## LightBar Screening and Armor Matching
In order to obtain the position of the armor stably, we first need to binarize the image. In the competition, the light bar of the armor of the target robot will only be red or blue, so we first take the image of the blue channel/red channel for binarization, at the same time, in order to further improve the stability of the binarization, we then convert the original image to grayscale and then binarize it, and then finally, we will do the sum operation with the two binarized images to get the binarized image that we will use in the end.

<br />Then find the contours in the binarized image and get the outer rectangles of all the contours, and filter out all the regions that do not satisfy the conditions by the area, aspect ratio and tilt angle of the outer rectangles. Finally, all the light bars that pass the screening are matched two by two as an armor, and the armor is screened again by the distance between the two light bars, the tilt angle and the aspect ratio of the armor formed after matching, etc., to get all the regions in the figure that may be an armor and input them into the classifier for the final judgment.
<a name="spF3x"></a>
## Armor Classifier
In the game, there existed a total of eight types of armor plate, and we also added a class for negative samples, the armor looks like numbers and some simple images, so we chose to go to build a very small CNN to carry out classification. The network consists of three convolutional and downsampling layers, and two fully connected layers, the specific network structure is as follows:<br />![全连接神经网络结构图.png](/assets/img/posts/ArmorClassify-CNN.png)
<a name="h81tK"></a>

# Project effect

<a name="Iarvm"></a>

## Algorithm performance

| **FPS on Intel NUC** | **Precision** | **Recall** |
| :---: | :---: | :---: |
| 150+FPS | 97% | 99% |
{:data-align="center"}


<a name="ejvUe"></a>

## Overall effect of algorithm
<img src="/assets/img/posts/ArmorClassify-Effect.png" style="width:70%;">
<a name="gI1fk"></a>

## CNN accuracy and confusion matrix
<img src="/assets/img/posts/ArmorClassify-AccuracyCurve.png" style="width:45%;">
<img src="/assets/img/posts/ArmorClassify-Matrix.png" style="width:40%;">


