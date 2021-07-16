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

 3. Set TurtleBot3 Model Name

choose the Trurtlebot you want to work with:

In case of TurtleBot3 Burger

`echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc`

In case of TurtleBot3 Waffle Pi

`echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashr`

## 2.Simulation
## Gazebo Simulation
## 1.Install Simulation Package
`$ cd ~/catkin_ws/src/`

`$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git`

`$ cd ~/catkin_ws && catkin_make`



## 2.Launch Simulation World
Three simulation environments are prepared for TurtleBot3. Please select one of these environments to launch Gazebo.



![2021-07-17](https://user-images.githubusercontent.com/85651071/126017239-d1c2c447-b114-4b1b-9d3d-a127da7aca18.png)




`$ export TURTLEBOT3_MODEL=burger`

`$ roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch`



![2021-07-17 (5)](https://user-images.githubusercontent.com/85651071/126017244-5ae9d53d-b768-4db8-b487-a40db0b6e610.png)



`$ export TURTLEBOT3_MODEL=waffle`

`$ roslaunch turtlebot3_gazebo turtlebot3_world.launch`



![2021-07-17 (4)](https://user-images.githubusercontent.com/85651071/126017252-e6f31e01-c06d-40cc-8868-541ec01fcda9.png)


`$ export TURTLEBOT3_MODEL=waffle_pi`

`$ roslaunch turtlebot3_gazebo turtlebot3_house.launch`















