# 16833 Advancing Dynamic Visual-Inertial SLAM
## A Comprehensive Exploration of Bundle Adjustment Techniques

This repository is dedicated to maintaining synchronization with the official implementation of the 16833 Capstone Project. It serves as the documentation hub for the project, ensuring that the information remains current and up-to-date.

The project aims at exploring different bundle adjustment techniques and their effects on dynamic slam. Traditional SLAM methods often assume static landmarks, leading to localization inaccuracies in dynamic environments where objects such as cars :car:, humans :runner:, buses :bus:, etc., are present. Building upon the DynaVINS [paper][arXivlink] , our project aims to address and improve dynamic SLAM challenges.

* The BA module validated on [VIODE dataset][VIODElink] dataset similar to DynaVINS.

<p align="center"><img src=readme_resource/city_main.gif alt="animated" width="30%"/>  <img src=readme_resource/parking_main.gif alt="animated" width="30%"/></p>

--- 

## Test Env.

This code is tested on

* Ubuntu 20.04.4 LTS
* ROS Noetic
* Ceres Solver 2.1
* OpenCV 4.6.0

## :package: Prerequisites

The dependency is equal to that of DynaVINS.

### **Support file from VINS-Fusion**

Due to the limiting file size of Github, we need **one** package and **two** files from the [VINS-Fusion repository](https://github.com/HKUST-Aerial-Robotics/VINS-Fusion/tree/master/support_files).

1. Set the `camera_models` package in your workspace, which is included in VINS-Fusion.
2. Copy `support_files/brief_k10L6.bin` in VINS-Fusion into our `support_files` folder 
3. Copy `support_files/brief_pattern.yml` in VINS-Fusion into our `support_files` folder

## :building_construction: How to build

> Please follow the below commands to build DynaVINS (on ROS).

``` bash
$ cd ~/catkin_ws/src 
$ git clone https://github.com/mansisarawata/dynaVINS_16833.git
$ cd ../
$ catkin_make  
(or if you use catkin tools) catkin build
$ source ~/catkin_ws/devel/setup.bash
```

## :runner: To run the demo codes

### VIODE dataset (Only BA) example

#### **VIODE sequence with monocular camera + IMU**

``` bash
$ roslaunch dynaVINS viode_mono.launch
$ rosbag play 3_high.bag (or 0_none.bag, 1_low.bag, ...)
```

---

## :mailbox: Contact Information

If you have any questions, please do not hesitate to contact us:

* [Mansi Sarawata] :envelope: `msarawat at andrew.cmu.edu`
* [Vedang Kokil] :envelope: `vkokil at andrew.cmu.edu`
* [Sriharan Balakrishnan] :envelope: `sriharab at andrew.cmu.edu`


[arXivlink]: https://arxiv.org/abs/2208.11500
[VIODElink]: https://github.com/kminoda/VIODE