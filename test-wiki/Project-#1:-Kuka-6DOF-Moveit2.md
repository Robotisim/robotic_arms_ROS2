## Issue Link [#1](https://github.com/Robotisim/robotic_arms_ROS2/issues/1)

### Project Overview
This package contains KUKA robotic arm using ROS2 and Moveit2. It includes capabilities for visualizing the robot's state, simulating its behavior in a 3D environment, planning and executing movements, and controlling the robot's actions. The package leverages several powerful tools in the ROS2 ecosystem, including RViz2 for visualization, Gazebo for simulation, and MoveIt2 for motion planning and control.

### Install Dependencies
- sudo apt-get install ros-humble-gazebo-ros
- sudo apt-get install ros-humble-gazebo-ros2-control
- sudo apt-get install ros-humble-control*
- sudo apt-get install ros-humble-gazebo-plugins
- sudo apt-get install ros-humble-moveit-visual-tools
- sudo apt-get install ros-humble-graph-msgs
- Moveit Installation [Link ](https://moveit.picknik.ai/humble/doc/tutorials/getting_started/getting_started.html)

### Running Project
- Clone the repository into your ROS2 workspace (if not done already) using:
    ```
    git clone -b running_projects https://github.com/Robotisim/robotic_arms_ROS2/tree/running_projects
    ```
- Build your workspace and source it ( assuming you are in worksapce root directory) , run the following command
    ```
    colcon build && source install/setup.bash
    ```
- Run the following command to launch the Kuka with Moveit RVIZ2 GUI for motion execution
    ```
    ros2 launch kuka_arm_pkg p1_c_moveit_kuka_arm.launch.py
    ```
- Run the node to send custom goals using Movegroup Interface
    ```
    ros2 run kuka_arm_pkg p1_b_moveit_drive
    ```
### Nodes
- **p1_a_joint_trajectory_controller.cpp**:
This file contains the implementation of a joint trajectory controller for the KUKA robotic arm. A joint trajectory controller is used to control the movement of a robot's joints along a specified trajectory.This  is part of the integration of MoveIt and Gazebo.

- **p1_b_motion_drive_moveit.cpp**:
 This file contains the implementation of a node that drives the motion of the KUKA robotic arm using MoveIt. This node is used for controlling the robot's movements.
### Launch Files
- **p1_a_rviz_kuka_arm.launch.py**: This file isused to initialize the RViz visualization tool with configurations specific to the KUKA robotic arm. RViz is a 3D visualizer for displaying sensor data and state information from ROS.

- **p1_b_gazebo_kuka_arm.launch.py**: This file is  used to start the Gazebo simulation environment with the KUKA robotic arm. Gazebo is a powerful 3D simulation environment for autonomous robots that is particularly useful for testing object-avoidance and computer vision.

- **p1_c_moveit_kuka_arm.launch.py**: This file is  used to start the MoveIt application with configurations specific to the KUKA robotic arm. MoveIt is a flexible framework for integrating motion planning, manipulation, 3D perception, kinematics, control, and navigation.

- **p1_d_moveit_node_controlling.launch.py**: This file is  used to start a node that controls the KUKA robotic arm using MoveIt. This could involve sending commands to the robotic arm to perform specific movements or tasks.

### Learning Outcomes
- Bringing robotic Arms into Gazebo Simulation
- Integerating ROS2_Controll into URDF
- Running Moveit with Robotic Arms in ROS2
---