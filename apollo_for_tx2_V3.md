---
title: apollo_for_tx2_V3
tags: Apollo,TX2,Q&A
grammar_cjkRuby: true
---
 
 # Apollo for TX2教程 #

# 一．	硬件准备
## 1.	设置TX2 CAN
CAN是实现车辆控制的主要总线和通信协议，本节对其的硬件配置进行描述。Jetson TX2有两个CAN控制器，支持在多个CAN节点间通信。为了使用CAN通信，必须确保CAN收发器与每个控制器连接。CAN收发器是控制器局域网（CAN）协议控制器和物理总线之间的接口。关于快速设置TX2 CAN，请参考《如何使用TX2上的CAN》和《TX2与canbus通讯》

# 二．软件准备 
## 2.	安装与配置Docker 
Docker 是一个开源的应用容器引擎，让开发者可以打包他们的应用以及依赖包到一个可移植的容器中，然后发布到任何流行的 Linux机器上(需要注意的是，该容器并不能完全实现跨平台架构移植)，也可以实现虚拟化。容器是完全使用沙箱机制，相互之间不会有任何接口。
 	Apollo使用的软件环境大部分基于ubuntu14，因此需要搭建一个基于arm64/ubuntu14的环境。详细安装与配置，请参考《如何安装与配置docker for Apollo on TX2》

## 3.	构建DEV镜像
Docker Image是一个特殊的文件系统，除了提供容器运行时所需的程序、库、资源、配置等文件外，还包含了为运行时准备的一些配置参数，基于Docker Image制作的dev镜像为Apollo开发提供了必须的工具和底层依赖库，通过这些库，可以对Apollo进行编译、运行甚至定制化。详细创建docker images的方法，请参考《如何创建docker image》和《如何构建dev镜像》

# 三．编译启动 
## 1.	Apollo-platform编译
Apollo-platform是Apollo工程的主要运行环境，主要包含Apollo专用ROS环境以及一些机器学习相关的库，请参考《如何编译Apollo-platform》实现编译。

## 2.	Apollo-kernel编译
Apollo-kernel是使用的linux的软实时插件的linux内核，对自动驾驶提供了更专业的调度支持，请参考《如何编译Apollo-kernal》实现编译。

## 3.	Apollo编译
Apollo是无人驾驶主要的工程部分，包含驱动，环境识别和驾驶算法等主要模块。
Apollo编译涉及很多依赖以及驱动编译和安装，详细的安装步骤请参考《如何在TX2上编译运行Apollo3.0》

## 4.	编译常见问题
请参考《Apollo for TX2问答》

# 四．上车验证 
Apollo for TX2分别在MKZ和请参考《TX2上车调试步骤》

