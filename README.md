## Turtlebot3 -gazebo & SLAM
This project aims to simulate how the robot discovers its environment in Gazebo while constructing it as a map using SLAM. This is accomplished through the use of an online version of ROS (https://app.theconstructsim.com/#/Home) along with robots from Turtlebot (https://emanual.robotis.com/docs/en/platform/turtlebot3/overview/).

## 1.PC setup
1. Install Dependent ROS 1 Packages
````
```
 $ sudo apt-get install ros-kinetic-joy ros-kinetic-teleop-twist-joy \
  ros-kinetic-teleop-twist-keyboard ros-kinetic-laser-proc \
  ros-kinetic-rgbd-launch ros-kinetic-depthimage-to-laserscan \
  ros-kinetic-rosserial-arduino ros-kinetic-rosserial-python \
  ros-kinetic-rosserial-server ros-kinetic-rosserial-client \
  ros-kinetic-rosserial-msgs ros-kinetic-amcl ros-kinetic-map-server \
  ros-kinetic-move-base ros-kinetic-urdf ros-kinetic-xacro \
  ros-kinetic-compressed-image-transport ros-kinetic-rqt* \
  ros-kinetic-gmapping ros-kinetic-navigation ros-kinetic-interactive-markers 
  ```
  ````
2. Install TurtleBot3 Packages

`$ sudo apt-get install ros-melodic-dynamixel-sdk`

`$ sudo apt-get install ros-melodic-turtlebot3-msgs`

`$ sudo apt-get install ros-melodic-turtlebot3`

## 2.Install Simulation Package
$ cd ~/catkin_ws/src/
$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make

choose the Trurtlebot you want to work with:

In case of TurtleBot3 Burger

echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
In case of TurtleBot3 Waffle Pi

echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc

## 3.Launch Simulation World
Three simulation environments are prepared for TurtleBot3. Please select one of these environments to launch Gazebo.


![2021-07-17](https://user-images.githubusercontent.com/85651071/126015680-91ceddad-b11a-4293-9989-c42252fe19a7.png)

$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch


![2021-07-17 (1)](https://user-images.githubusercontent.com/85651071/126016227-18e18c2a-e964-4809-9aef-28010dfb9963.png)

$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch


![2021-07-17 (2)](https://user-images.githubusercontent.com/85651071/126016274-097323d9-be39-46be-96ed-a002c5472136.png)

$ export TURTLEBOT3_MODEL=waffle_pi
$ roslaunch turtlebot3_gazebo turtlebot3_house.launch















