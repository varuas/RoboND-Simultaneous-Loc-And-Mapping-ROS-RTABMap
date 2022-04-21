# RoboND-Map-My-World

This project involves the creation of a 2D occupancy grid and a 3D octomap from a simulated environment using ROS and RTAB-Map. It is a POC to explore how to do Simulataneous Localization and Mapping (SLAM) in ROS.


RTAB-Map (Real-Time Appearance-Based Mapping) is a popular solution for SLAM to develop robots that can map environments in 3D. RTAB-Map has good speed and memory management, and it provides custom developed tools for information analysis. 

This project uses the rtabmap_ros package, which is a ROS wrapper (API) for interacting with RTAB-Map. Here, a custom ROS package is created to interface with the rtabmap_ros package. 

When the robot is launched we can teleop around the room to generate a proper map of the environment.
