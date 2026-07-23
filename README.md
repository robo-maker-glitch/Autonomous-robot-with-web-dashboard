# 🤖 Autonomous Box Bot with Web Dashboard

An autonomous differential-drive ROS 2 robot featuring LiDAR-based obstacle avoidance in enclosed environments, paired with a real-time Flask web dashboard for live camera streaming and radar telemetry.

---

## 📌 Project Overview

This project elevates simple simulation into a complete autonomous system. The **Autonomous Box Bot** navigates within bounded walls, dynamically dodging obstacles using a 2D LiDAR sensor. To monitor the robot's performance remotely, a **Flask web application** runs alongside ROS 2, providing a real-time feed of the onboard camera and a live radar telemetry interface.

---

## ✨ Key Features

* **Autonomous Navigation:** Reactive LiDAR-based obstacle avoidance node (`obstacle_avoider.py`) operating in real-time.
* **Live Telemetry Web App:** Flask dashboard streaming live video feed (`/camera/image_raw`) and laser scanner visualization.
* **Enclosed World Simulation:** Custom Gazebo environment (`enclosed_world.sdf`) with surrounding walls and unpredictable obstacles.
* **Modular Description:** Flexible robot model constructed via `robot.urdf.xacro`.
* **Terminal Diagnostic HUD:** Lightweight terminal visualizer (`terminal_viewer.py`) for quick CLI debugging.

---

## 🛠️ System Architecture

```text
ros2_box_robot_ws/
└── src/
    └── box_robot_sim/
        ├── box_robot_sim/
        │   ├── obstacle_avoider.py    # Reactive LiDAR control node
        │   ├── terminal_viewer.py     # Terminal visualizer HUD
        │   └── web_dashboard.py       # Flask server & teleop interface
        ├── description/
        │   └── robot.urdf.xacro       # Kinematics, LiDAR & Camera sensors
        ├── launch/
        │   └── robot_sim.launch.py    # Master launch file
        └── worlds/
            └── enclosed_world.sdf     # Enclosed Gazebo arena
