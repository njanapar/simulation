# Robocar Deployment on Gazebo using ROS2

## Prerequisites

Before setting up the environment, ensure that the following tools are installed:

- **VirtualBox** for creating virtual machines.
- **ROS2** (Robot Operating System) for developing the robocar application.
- **Gazebo** for simulating the robocar in a 3D environment.

---

## Installation Guide

### 1. Installing VirtualBox

Download VirtualBox from the official website:

- [VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)

Follow the installation steps for your operating system.

**Screenshot**: ![VirtualBox Installation](./images/virtualbox_installation.png)

### 2. Installing ROS2

Install ROS2 by following the instructions specific to your OS.

- **ROS2 Installation Guide**: [ROS2 Installation](https://docs.ros.org/en/foxy/Installation.html)

### 3. Installing Gazebo

Gazebo is a simulation software that integrates well with ROS2. Install Gazebo by following the steps in the official guide.

- **Gazebo Installation Guide**: [Gazebo Installation](http://gazebosim.org/)

After installation, you can verify it by running the following command:

```bash
gazebo
---

## Conclusion

You have successfully set up a robocar simulation in Gazebo with ROS2! You can now extend the simulation and modify the control scripts to create more complex behaviors and interactions for your robocar.

---

## Troubleshooting

If you encounter any issues during installation or while running the simulation, please refer to the following:

### 1. **ROS2 Workspace Issues**
   - Ensure that ROS2 is properly sourced by running the following command:

   ```bash
   source /opt/ros/foxy/setup.bash
## Deploying the Robocar in Gazebo

To deploy a robocar in a simple environment, follow these steps:

### 1. Setup ROS2 Workspace
Create a ROS2 workspace if you don't have one already.

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src
colcon build
## Add Robocar Package

Clone a robocar simulation package into your workspace:

```bash
cd ~/ros2_ws/src
git clone https://github.com/ros2/robocar_simulation.git
cd ~/ros2_ws
colcon build
## Launch the Gazebo Simulation

To launch the robocar simulation in Gazebo, use the following command:

```bash
source ~/ros2_ws/install/setup.bash
ros2 launch robocar_simulation gazebo_launch.py
## Control the Robocar

You can use ROS2 to control the robocar in Gazebo with sample scripts. Below is a basic script to control the robocar's movements:

```python
import rclpy
from geometry_msgs.msg import Twist
from rclpy.node import Node

class RobocarController(Node):
    def __init__(self):
        super().__init__('robocar_controller')
        self.publisher = self.create_publisher(Twist, 'cmd_vel', 10)
        self.timer = self.create_timer(0.1, self.move_forward)

    def move_forward(self):
        msg = Twist()
        msg.linear.x = 0.5  # Move forward at 0.5 m/s
        self.publisher.publish(msg)

def main(args=None):
    rclpy.init(args=args)
    robocar_controller = RobocarController()
    rclpy.spin(robocar_controller)
    robocar_controller.destroy_node()
    rclpy.shutdown()

if __name__ == '__main__':
    main()
## To run the script:

```bash
ros2 run robocar_simulation robocar_controller.py

