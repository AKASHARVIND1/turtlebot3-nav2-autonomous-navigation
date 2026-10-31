# TurtleBot3 Autonomous Navigation using ROS 2 Nav2

## Overview
This project demonstrates autonomous navigation of a TurtleBot3 Waffle robot using ROS 2 Humble, Gazebo Classic and Navigation2 (Nav2).

The robot uses LiDAR sensor data, AMCL localization and Nav2 path planning to navigate a simulated environment and reach selected goals.

## Environment
- Ubuntu 22.04 (WSL2)
- ROS 2 Humble
- TurtleBot3 Waffle
- Gazebo Classic 11
- Navigation2 (Nav2)
- RViz2

## Repository Structure
- `launch/`: Navigation launch file
- `config/`: Waffle navigation parameters
- `map/`: Map image and YAML metadata
- `rviz/`: RViz visualization configuration

## Setup
Install ROS 2 Humble and the TurtleBot3 simulation and navigation packages.

Source ROS 2:

```bash
source /opt/ros/humble/setup.bash
export TURTLEBOT3_MODEL=waffle
