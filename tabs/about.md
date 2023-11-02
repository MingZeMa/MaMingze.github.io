---
layout: about
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_about

# image for page specific usage
img: ":about.jpg"
# publish date (used for seo)
# if not specified, site.time will be used.
#date: 2022-03-03 12:32:00 +0000

# for override items in _data/lang/[language].yml
#title: My title
#button_name: "My button"
# for override side_and_top_nav_buttons in _data/conf/main.yml
#icon: "fa fa-bath"

# seo
# if not specified, date will be used.
#meta_modify_date: 2022-03-03 12:32:00 +0000
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

{%- comment -%} Please delete below and place your page content here {%- endcomment -%}


<div align='center'>
    <span style="font-weight: bold;color: #3873b2;font-size: 40px;">
        Ma Mingze
    </span>
</div>

<div align='center'>
    <span style="font-weight: bold;color: grey;font-size: 15px;">
        Email: hit.mamingze@gmail.com | Phone: (+86) 182-9910-5161
    </span>
</div>


<!-- Education -------------- -->

<div align='left' style="margin-top: 20px;margin-bottom: 10px;">
    <span style="font-weight: bold;color: #3873b2;font-size: 25px;">
        Education
    </span>
    <hr style="border-color: #3873b2;margin-top: 0;">
</div>

<div style="display: flex; justify-content: space-between;margin-top: 0px;font-size: 15px;font-weight: bold;">
<span>Harbin Institute of Technology, Weihai</span>
<span> 09.2020 - 07.2024</span>
</div>

- Degree:Bachelor of Engineering
- Major: Welding Technology and Engineering 
- GPA: 82.19 / 100


<!-- Main Experience -------------- -->

<div align='left' style="margin-top: 20px;margin-bottom: 10px;">
    <span style="font-weight: bold;color: #3873b2;font-size: 25px;">
        Main Experience
    </span>
    <hr style="border-color: #3873b2;margin-top: 0;">
</div>


<!-- HERO1 ##################################### -->
<div style="display: flex; justify-content: space-between;margin-top: 0px;font-size: 15px;font-weight: bold;">
<span>HERO Competitive Robot</span>
<span> 06.2022 - Present </span>
</div>

_Team – Captain_

- Assumed role of Captain for the new season, demonstrating exceptional leadership in overall management and establishment of structured cross-management between military and technical groups;
- Formulated and implemented a project workflow tailored to team needs, resulting in significant improvement in teamwork efficiency;
- Managed and led project promotional efforts pertinent to the vision group, demonstrating adeptness in task management and teamwork.


<!-- HERO2 ##################################### -->
<div style="display: flex; justify-content: space-between;margin-top: 0px;font-size: 15px;font-weight: bold;">
<span>HERO Competitive Robot</span>
<span> 09.2021 - 06.2022 </span>
</div>

_Team Member of the Vision Group_

- Participated in the transformative RoboMaster 2022 competition as a pioneering member of the vision group;
- Assisted team leader and Captain in optimizing the vision group's project development and training processes;
- Led the development of an intricate robot vision algorithm with primary responsibility for the creation of a self-aiming framework;
- Designed and constructed a high-level radar system algorithm, substantially contributing to overall team performance.

<!-- 718 ##################################### -->
<div style="display: flex; justify-content: space-between;margin-top: 0px;font-size: 15px;font-weight: bold;">
<span>718 Smart Car Lab</span>
<span> 12.2020 - 05.2022 </span>
</div>

_Team Leader_

The lab is known as the cradle of scientific innovation in the school, as it systematically uses intelligent car competitions to
develop first-year students' skills. This initiative, a talent pipeline for various advanced laboratories, draws an annual
audience exceeding 1,000 individuals.
- Enhanced team cohesion and improved overall atmosphere during tenure;
- Revamped team training system, transitioning from traditional oral methods to a more efficient online self-learning
platform;
- Implemented regular assessment techniques, significantly reducing training-associated labor costs.



<!-- Research Experience -------------- -->

<div align='left' style="margin-top: 20px;margin-bottom: 10px;">
    <span style="font-weight: bold;color: #3873b2;font-size: 25px;">
        Research Experience
    </span>
    <hr style="border-color: #3873b2;margin-top: 0;">
</div>


<!-- CNN ########################## -->
<div style="display: flex; justify-content: space-between;margin-top: 0px;font-size: 15px;font-weight: bold;">
<span>HERO Competitive Robot Team, Robot armor detection algorithm based on OpenCV and CNN</span>
<span> 09.2021 - Present </span>
</div>

_Project Leader_

In the RoboMaster competition, accurately aiming at the enemy robot's four armor plates is crucial. This automated process involves extracting the coordinates of the armor plates' four corner points. 
- Developed a robust two-stage object detection algorithm, leveraging geometric feature extraction and CNN-based classification. The algorithm demonstrated exceptional performance with a recall rate of 98% and 100% precision, achieving over 150FPS on 640x480 resolution imagery.

<!-- RUNE ########################## -->
<div style="display: flex; justify-content: space-between;margin-top: 0px;font-size: 15px;font-weight: bold;">
<span>HERO Competitive Robot Team, Rune detection algorithm based on YOLOX and RTM-Pose</span>
<span> 09.2021 - Present </span>
</div>

_Project Leader_

This contest aims to accurately hit five rotating fan blades, each 8m away, in a specific sequence. The task includes creating a highly robust identifier to determine the coordinates of the fan blades' four corners and establishing the fan blades' category.
- Implemented a top-down key point detection algorithm for power rune fan blades using cutting-edge YOLOX and RTM-Pose technologies;
- Enhanced original YOLOX Backbone with ShuffleNetV2, effectively reducing parameter number while maintaining model reliability;
- Streamlined model deployment on MiniPC using advanced OpenVINO technology, significantly improving operational efficiency;
- Increased model running speed by 50% via int8 quantization, optimizing Power Rune detection processes.
- Completed comprehensive identification of all fan blades within the Power Rune in a remarkable 12ms, vastly improving project timelines.

<!-- NTU ########################## -->
<div style="display: flex; justify-content: space-between;margin-top: 0px;font-size: 15px;font-weight: bold;">
<span>NTU Business AI Lab, Tumor classification model based on ResNet-50</span>
<span> 01.2023 - 03.2023 </span>
</div>

_Modeler_

- Managed model construction and experimentation for a project focusing on classifying four distinct tumor types leveraging the ResNet-50 network architecture;
- Conducted comprehensively comparing different data enhancement measures, including geometric transformation, MixUp, and SamplePairing;
- Successfully achieved a notable improvement in the model's accuracy, hitting a peak of 98% on the test set.


<!-- 718 ########################## -->
<div style="display: flex; justify-content: space-between;margin-top: 0px;font-size: 15px;font-weight: bold;">
<span>718 Smart Car Lab, Lane detection and tracking algorithm based on UNet</span>
<span> 12.2020 - 08.2021 </span>
</div>

_Project Leader_

- Implemented an intelligent logistics car model based on Jetson Nano, incorporating multiple functionalities such as Lidar mapping navigation, obstacle evasion, shortest path planning, and recognition of traffic lights and lane lines;
- Utilized UNet-based lane line recognition system and calculated coordinates for lane line points for efficient curve fitting;
- Devised calculation of car's horizontal offset from the lane line to determine optimal turning angle; effectively ensured automatic tracking along lane lines;
- Successfully achieved consistent lane line recognition across varying lighting conditions and maintained stable tracking at a speed of 1m/s.


<!-- Honors and Awards -------------- -->

<div align='left' style="margin-top: 20px;margin-bottom: 10px;">
    <span style="font-weight: bold;color: #3873b2;font-size: 25px;">
        Honors and Awards
    </span>
    <hr style="border-color: #3873b2;margin-top: 0;">
</div>

<div style="display: flex; justify-content: space-between;margin-top: 0px;">
<span>• 1st Place, RoboMaster University Championship 2023 Robot Combat Award</span>
<span> 08.2023 </span>
</div>

<div style="display: flex; justify-content: space-between;margin-top: 0px;">
<span>• 2nd Place, RoboMaster University Championship 2023 National Competition</span>
<span> 08.2023 </span>
</div>

<div style="display: flex; justify-content: space-between;margin-top: 0px;">
<span>• 1st Place, RoboMaster University Championship 2023 Regional Competition , Central region</span>
<span> 06.2023 </span>
</div>

<div style="display: flex; justify-content: space-between;margin-top: 0px;">
<span>• 1st Place, RoboMaster University Technical Challenge 2022 National Competition</span>
<span> 06.2022 </span>
</div>

<div style="display: flex; justify-content: space-between;margin-top: 0px;">
<span>• 1st Place, RoboMaster University Championship 2022 Regional Competition , East region</span>
<span> 06.2022 </span>
</div>

<div style="display: flex; justify-content: space-between;margin-top: 0px;">
<span>• 2nd Place, RoboMaster University Championship 2022 National Competition </span>
<span> 08.2022 </span>
</div>

<div style="display: flex; justify-content: space-between;margin-top: 0px;">
<span>• 2nd Place, RoboMaster University Championship 2022 Robot Combat Award</span>
<span> 08.2022 </span>
</div>

<div style="display: flex; justify-content: space-between;margin-top: 0px;">
<span>• 3rd Place, National College Student Intelligent Car Competition North Zone Competition</span>
<span> 07.2021 </span>
</div>

<div style="display: flex; justify-content: space-between;margin-top: 0px;">
<span>• 3rd Place, National College Student Electronic Design Competition Shandong Division</span>
<span> 10.2021 </span>
</div>




<!-- IT Skills -------------- -->

<div align='left' style="margin-top: 20px;margin-bottom: 10px;">
    <span style="font-weight: bold;color: #3873b2;font-size: 25px;">
        IT Skills
    </span>
    <hr style="border-color: #3873b2;margin-top: 0;">
</div>

<div style="display: flex;">
    <div style="flex: 0 0 60%; margin-top: 0px;margin-bottom: 0px;">
        <p style="margin: 0.1em 0;">
        <span style="font-weight: bold;color: black;font-size: 13px;">
            • Programming language: Python > C++ > C
        </span>
        </p >
        <p style="margin: 0.1em 0;">
        <span style="font-weight: bold;color: black;font-size: 13px;">
            • Programming skills: PyTorch, OpenVINO, OpenCV, ROS, Docker, Qt
        </span>
        </p>
    </div>
    <div style="flex: 0 0 60%; margin-top: 0px;margin-bottom: 0px;">
        <p style="margin: 0.1em 0;">
        <span style="font-weight: bold;color: black;font-size: 13px;">
            • Software tools: MATLAB, Keil, Solidworks, AutoCAD
        </span>
        </p>
        <p style="margin: 0.1em 0;">
        <span style="font-weight: bold;color: black;font-size: 13px;">
            • Embedded Real-Time Systems (RTOS): RT-Thread
        </span>
        </p>
    </div>
</div>
