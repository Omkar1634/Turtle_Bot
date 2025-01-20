# Fuzzy and PID Control for Robotics

This repository contains implementations of fuzzy logic and PID (Proportional-Integral-Derivative) control systems for obstacle avoidance and edge following in robotic applications using ROS 2.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [File Descriptions](#file-descriptions)
- [Contributing](#contributing)
- [License](#license)

---

## Overview
This project demonstrates the use of fuzzy logic and PID control to guide a robot safely and efficiently in dynamic environments. It uses input from LIDAR sensors to:

- Avoid obstacles
- Follow edges (like walls)
- Maintain stability using PID control

### Key Control Techniques
1. **Fuzzy Logic**: Implements fuzzy rules for obstacle avoidance and edge following.
2. **PID Control**: Adjusts robot motion based on error feedback to ensure smooth navigation.

---

## Features
- **Obstacle Avoidance**: Determines the optimal path based on sensor input.
- **Edge Following**: Keeps the robot at a consistent distance from a wall or edge.
- **Customizable Membership Functions**: Allows fine-tuning of fuzzy logic behavior.
- **ROS 2 Integration**: Utilizes ROS 2 nodes, topics, and QoS for real-time robot control.

---

## Dependencies
Ensure you have the following installed:

- Python 3.x
- ROS 2 (Foxy, Humble, or newer)
- `sensor_msgs`, `geometry_msgs`, `nav_msgs`

To install ROS 2, follow the official [ROS 2 Installation Guide](https://docs.ros.org/en/foxy/Installation.html).

---

## Usage
1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. Build the ROS 2 workspace:
   ```bash
   colcon build
   ```

3. Source the workspace:
   ```bash
   source install/setup.bash
   ```

4. Run the desired script (e.g., Fuzzy Obstacle Avoidance):
   ```bash
   ros2 run <package_name> fuzzy_object_avoidance
   ```

---

## File Descriptions
### 1. `Fuzzy_Integration.py`
Combines fuzzy logic methods to achieve both obstacle avoidance and edge following. This file integrates:

- Membership functions for front, left, right sensors.
- Fuzzy rule definitions for speed and turning.

### 2. `Fuzzy_Object_Avoidance.py`
Focused on obstacle avoidance:

- Uses front, left, and right LIDAR sensors to determine the robot's proximity to obstacles.
- Fuzzy rules dynamically calculate turning angles and speed.

### 3. `Fuzzy_Right_Edge.py`
Specialized in right-edge following:

- Maintains a consistent distance from the right wall using front-right and back-right sensors.
- Includes customizable membership functions and rules for turning and speed adjustment.

### 4. `PID.py`
Implements PID control:

- Calculates errors based on desired and actual distances.
- Adjusts the robot's angular velocity to minimize error.
- Features proportional, integral, and derivative tuning parameters.

---

## Contributing
Contributions are welcome! If you have suggestions or improvements, please:

1. Fork the repository.
2. Create a new branch.
3. Submit a pull request.

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Acknowledgments
- [ROS Community](https://ros.org) for resources and documentation.
- Open-source contributors for inspiration and code structure.
