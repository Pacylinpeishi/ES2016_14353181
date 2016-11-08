##Lab5-Install ROS

###【个人信息】

姓名：林佩诗

学号：14353181

完成日期：2016/10/25

###【简介】

ROS（Robot operation system），机器人操作系统，是开源的，是用于机器人的一种后操作系统，或者说次级操作系统。它提供类似操作系统所提供的功能，包含硬件抽象描述、底层驱动程序管理、共用功能的执行、程序间的消息传递、程序发行包管理，它也提供一些工具程序和库用于获取、建立、编写和运行多机整合的程序。作为一套框架，底层提供硬件驱动，软件层面支持通用的文件格式。

###【实验步骤】

#####1. Configure your Ubuntu repositories

Configure your Ubuntu repositories to allow "restricted"， "universe" and "multiverse".

![1.PNG](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/lab5_image/1.PNG?raw=true)

#####2. Setup your sources.list

Setup your computer to accept software from packages.ros.org. ROS Jade ONLY supports Trusty (14.04), Utopic (14.10) and Vivid (15.04) for debian packages. 

######$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

#####3. Set up your keys

######$ sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116

![2.PNG](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/lab5_image/2.PNG?raw=true)

#####4. Installation

First, make sure your Debian package index is up-to-date: 

######$ sudo apt-get update

![3.PNG]()

There are many different libraries and tools in ROS. We provided four default configurations to get you started. You can also install ROS packages individually. 

Desktop-Full Install: (Recommended) : ROS, rqt, rviz, robot-generic libraries, 2D/3D simulators, navigation and 2D/3D perception.

######$ sudo apt-get install ros-jade-desktop-full

![4.PNG]()

Desktop Install: ROS, rqt, rviz, and robot-generic libraries 

######$ sudo apt-get install ros-jade-desktop

![5.PNG]()

ROS-Base: (Bare Bones) ROS package, build, and communication libraries. No GUI tools.

######$ sudo apt-get install ros-jade-ros-base

![6.PNG]()

Individual Package: You can also install a specific ROS package (replace underscores with dashes of the package name):

######$ sudo apt-get install ros-jade-PACKAGE

e.g. 

######$ sudo apt-get install ros-jade-slam-gmapping

![7.PNG]()

#####5. Initialize rosdep

Before you can use ROS, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS. 

######$ sudo rosdep init

![8.PNG](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/lab5_image/5.PNG?raw=true)

######$ rosdep update

![9.PNG](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/lab5_image/6.PNG?raw=true)

#####6. Environment setup

It's convenient if the ROS environment variables are automatically added to your bash session every time a new shell is launched: 

######$ echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc

######$ source ~/.bashrc

If you have more than one ROS distribution installed, ~/.bashrc must only source the setup.bash for the version you are currently using.

If you just want to change the environment of your current shell, you can type: 

######$ source /opt/ros/jade/setup.bash

######7. Getting rosinstall

rosinstall is a frequently used command-line tool in ROS that is distributed separately. It enables you to easily download many source trees for ROS packages with one command. 

To install this tool on Ubuntu, run: 

######$ sudo apt-get install python-rosinstall

![10.PNG]()



