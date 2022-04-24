# RoboND-Map-My-World

This project involves the creation of a 2D occupancy grid and a 3D octomap from a simulated environment using ROS and RTAB-Map. It is a POC to explore how to do Simulataneous Localization and Mapping (SLAM) in ROS.

RTAB-Map (Real-Time Appearance-Based Mapping) is a popular solution for SLAM to develop robots that can map environments in 3D. RTAB-Map has good speed and memory management, and it provides custom developed tools for information analysis. 

This project uses the rtabmap_ros package, which is a ROS wrapper (API) for interacting with RTAB-Map. Here, a custom ROS package is created to interface with the rtabmap_ros package. 

When the robot is launched we can teleop around the room to generate a proper map of the environment.

### Description of the robot

The robot is a simulated differential drive robot created via URDF having the following sensors:

 - A 2D Laser, providing sensor_msgs/LaserScan messages
 - Odometry sensors, providing nav_msgs/Odometry messages
 - 3D Camera - generates RGB-D images

### ROS Packages used
 - rtabmap
 - rtabmapviz
 - ros-teleop
 - gazebo
 - rviz

### Launch 

Change to the catkin_ws directory and source the ROS Melodic environment:

    cd /mnt/Workspaces/RoboND-Map-My-World/catkin_ws
    source devel/setup.bash

#### Launch commands for SLAM:

`roslaunch my_robot world.launch`

`rosrun teleop_twist_keyboard teleop_twist_keyboard.py`

`roslaunch my_robot mapping.launch`

The map will be re-created everytime this is launched. 
We can find the map in the `maps` sub directory.

#### Launch command for visualizing the map
`rtabmap-databaseViewer /mnt/Workspaces/RoboND-Map-My-World/catkin_ws/src/my_robot/maps/rtabmap.db`

#### Launch commands for Localization

`roslaunch my_robot localization.launch`

### Real Time Visulization

 - Another tool that we can use is rtabmapviz, which is an additional node for real time visualization of feature mapping, loop closures, and more.
 - It’s not recommended to use this tool while mapping in simulation due to the computing overhead.
 - rtabmapviz is great to deploy on a real robot during live mapping to ensure that we are getting the necessary features to complete loop closures.

To enable this visualization in this project, the `mapping.launch` file needs to be uncommented for the node `rtabmapviz`. 