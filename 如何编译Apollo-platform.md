---
title: 如何编译Apollo-platform
tags: Apollo,platform
grammar_cjkRuby: true
---

（1） 安装依赖库
首先安装libgtest-dev、python-empy,  python-nose, libtheora-dev, libogg-dev, libgstreamer-plugins-base0.10-dev, libgstreamer0.10-dev（支持audio框架）。
安装依赖包的命令如下：
```
# apt-get install libgstreamer0.10-dev
# apt-get install libgstreamer-plugins-base0.10-dev
# apt-get install ligogg-dev
# apt-get install libtheora-dev
# apt-get install python-empy python-nose
```
（2） PCL编译安装
ros依赖PCL，需要重新编译PCL的aarch64版本。编译方法如下：
```
a)	安装依赖的库文件，比如gtest，boost，eigen， flann，HDF5，VTK等。
b)	下载PCL源码：https://github.com/PointCloudLibrary/pcl
c)	解压源码，并进入解压后的目录，然后执行如下命令：
  # mkdir build
  # cd build
  # cmake ../
如果编译release版本：
  # cmake -DCMAKE_BUILD_TYPE=Release ../
  # make & make install
  ```
（3） 修改编译脚本
在如下目录的CMakefiles.txt文件中添加include path (vision_opencv/cv_bridge/include)。
image_transport_plugin/compressed_depth_image_transport
image_transport_pligin/image_transport_plugin
（4） Apollo专用Ros的编译安装
运行如下命令
```
  # cd apollo-platform/ros
  # ./build.sh build
  ```
编译完成后需要将apollo-platform/ros/install/ros_aarch64拷贝到/home/tmp/目录下，并重命名为ros

