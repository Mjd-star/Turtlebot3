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






`$ export TURTLEBOT3_MODEL=burger`

`$ roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch`



![2021-07-17 (3)](https://user-images.githubusercontent.com/85651071/126552708-a32b653d-f32c-415f-b950-fe93453983b5.png)




`$ export TURTLEBOT3_MODEL=waffle`

`$ roslaunch turtlebot3_gazebo turtlebot3_world.launch`


![2021-07-17 (8)](https://user-images.githubusercontent.com/85651071/126553300-28e45e1d-7283-47b7-9050-fc1d31828ae5.png)



`$ export TURTLEBOT3_MODEL=waffle_pi`

`$ roslaunch turtlebot3_gazebo turtlebot3_house.launch`



![2021-07-17 (4)](https://user-images.githubusercontent.com/85651071/126553353-333e7571-8c62-4baf-a48f-e4a5173f6e83.png)




## SLAM Simulation
 ## 1.Launch Simulation World
 
` $ export TURTLEBOT3_MODEL=burger`

`$ roslaunch turtlebot3_gazebo turtlebot3_world.launch`



![2021-07-17 (8)](https://user-images.githubusercontent.com/85651071/126020735-09306751-4a67-4c52-b143-d89c1133f5f7.png)




## 2.Run SLAM Node
`$ export TURTLEBOT3_MODEL=burger`

`$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping`



![2021-07-17 (14)](https://user-images.githubusercontent.com/85651071/126048741-564e0b91-c7c2-4f2e-8f05-5ae287d892da.png)







## 3.Run Teleoperation Node
`$ export TURTLEBOT3_MODEL=burger`

`$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch`



![2021-07-17 (9)](https://user-images.githubusercontent.com/85651071/126020750-0cdbcafd-081b-4801-8d1e-5cd67de0f3c1.png)



## 4.Save Map
`$ rosrun map_server map_saver -f ~/map`

![2021-07-17 (17)](https://user-images.githubusercontent.com/85651071/126553935-a1f08e01-d2bc-4525-a32e-821e0443551f.png)



![2021-07-17 (14)](https://user-images.githubusercontent.com/85651071/126048758-9bb6483c-0956-4198-81cf-58c3d84c6b58.png)





