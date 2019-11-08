# Drone Mom
## CIS565 Final Project for John Marcao, Eric Micallef, and Taylor Nelms

### This guide will install everything you need to get started with ROS on the Jetson Nano development setup please refer to the readme in the setup folder.

## Do not clone this repo until the instructions tell you to.

you need to build a ROS workspace first...

## Installation

First, install the latest [JetPack](https://developer.nvidia.com/embedded/jetpack) on your Jetson (JetPack 4.2.2 for ROS Melodic or JetPack 3.3 for ROS Kinetic on TX1/TX2).

Once you are logged onto your jetson following the instructions below. 
### ROS Core

Install the `ros-melodic-ros-base`package on your Jetson following these directions:

https://www.stereolabs.com/blog/ros-and-nvidia-jetson-nano/

or follow these commands ( information on the commands is in link above )

```bash
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
$ sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
$ sudo apt update
$ sudo apt install ros-melodic-desktop
$ sudo rosdep init 
$ rosdep update
$ echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc 
$ source ~/.bashrc
```


Depending on which version of ROS you're using, install some additional dependencies:

#### ROS Melodic dependencies
```bash
$ sudo apt-get install ros-melodic-image-transport
$ sudo apt-get install ros-melodic-image-publisher
$ sudo apt-get install ros-melodic-vision-msgs
```

#### create Workspace

Now you must make the catkin workspace or the DroneMoM workspace. How ever you like to think about it.

Instructions can be found here:
http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment#Create_a_ROS_Workspace

Or follow these commands. The workspace can be created where ever you are most comfortable below is an example of mind.

```bash
$ mkdir -p ~/CIS565/droneMoM_ws/src
$ cd ~/CIS565/droneMoM_ws/
$ catkin_make
$ catkin_make -DPYTHON_EXECUTABLE=/usr/bin/python3 -DPYTHON_INCLUDE_DIR=/usr/include/python3.7m -DPYTHON_LIBRARY=/usr/lib/libpython3.7m.so
$ source devel/setup.bash
$ echo $ROS_PACKAGE_PATH
```

Ensure that the path from the echo output matches your path. Should be something like

/home/youruser/CIS565/droneMoM_ws/src:/opt/ros/melodic/share

### Clone!

Now you can clone this repo into the src folder of your newly crated ros workspace!

### Build 

navigate to your workspace so ~/CIS565/droneMoM_ws/src

and type 'catkin_make' This will build everything. Ensure there are no errors. Report to me if there are.

That is it!

### catkin commands

catkin_make
catkin_make clean





