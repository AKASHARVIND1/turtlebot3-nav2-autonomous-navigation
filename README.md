# TurtleBot3 Autonomous Navigation using ROS 2 Nav2

## Project Overview

This project demonstrates autonomous navigation using the TurtleBot3 Waffle robot in a simulated Gazebo environment with ROS 2 Humble and the Navigation2 (Nav2) stack.

The robot uses LiDAR sensor data and localization to navigate through a mapped environment, plan paths, and reach selected navigation goals autonomously.

## Technologies Used

- ROS 2 Humble
- Ubuntu 22.04 (WSL2)
- TurtleBot3 Waffle
- Gazebo Classic 11
- Navigation2 (Nav2)
- RViz2
- Python

## Features

- TurtleBot3 simulation in Gazebo
- 2D map visualization in RViz2
- LiDAR-based obstacle sensing
- AMCL-based localization
- Global and local path planning
- Autonomous navigation using Nav2
- Goal completion feedback

## System Setup

**Environment:**
- OS: Ubuntu 22.04 on WSL2
- ROS 2 Distribution: Humble
- Robot Model: Waffle
- Simulator: Gazebo Classic

## Running the Simulation

Open separate Ubuntu terminals for the following steps.

### 1. Start Gazebo Server

```bash
source /opt/ros/humble/setup.bash
export TURTLEBOT3_MODEL=waffle
export GAZEBO_PLUGIN_PATH=/opt/ros/humble/lib

gzserver --verbose \
-s libgazebo_ros_init.so \
-s libgazebo_ros_factory.so \
-s libgazebo_ros_force_system.so \
/opt/ros/humble/share/turtlebot3_gazebo/worlds/turtlebot3_world.world
```

### 2. Start Gazebo Client

```bash
gzclient
```

### 3. Spawn TurtleBot3

```bash
source /opt/ros/humble/setup.bash
export TURTLEBOT3_MODEL=waffle

ros2 launch turtlebot3_gazebo spawn_turtlebot3.launch.py
```

### 4. Start Navigation2

```bash
source /opt/ros/humble/setup.bash
export TURTLEBOT3_MODEL=waffle

ros2 launch turtlebot3_navigation2 navigation2.launch.py use_sim_time:=True
```

### 5. Start Robot State Publisher

```bash
source /opt/ros/humble/setup.bash
export TURTLEBOT3_MODEL=waffle

ros2 launch turtlebot3_gazebo robot_state_publisher.launch.py
```

## How to Demonstrate Autonomous Navigation

1. Start the Gazebo simulation and RViz2.
2. Set the initial robot pose using the 2D Pose Estimate tool in RViz2.
3. Select a destination using the Nav2 Goal tool.
4. Observe the robot planning and following its path.
5. Verify successful goal completion in the Navigation2 panel.

## Project Outcome

The TurtleBot3 Waffle robot was successfully simulated using Gazebo Classic and ROS 2 Humble. The Nav2 stack successfully planned and executed an autonomous navigation goal, with the terminal reporting:

`[bt_navigator]: Goal succeeded`

## Author

**Akash Aravind**

B.Tech – Robotic Engineering  
Garden City University

GitHub: https://github.com/AKASHARVIND1
