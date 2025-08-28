# Week 2 Task – ROS2 Topics & Teleoperation with TurtleBot3

## Steps & Commands

### 1. Launch TurtleBot3 in Gazebo
```bash
export TURTLEBOT3_MODEL=burger
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py

#Teleport the Robot
ros2 run turtlebot3_teleop teleop_keyboard
Keys used are: W/A/S/D/X

#Explore Topics
ros2 topic list
ros2 topic info /cmd_vel
ros2 topic echo /odom --once
ros2 topic hz /scan


#Inspect Messsage Structure
ros2 interface show geometry_msgs/msg/Twist
ros2 interface show sensor_msgs/msg/LaserScan

#Visualize in RViz2
rviz2
Add: TF, RobotModel, LaserScan, Odometry


#Record & Replay Data
ros2 bag record -o my_teleop_bag /scan /odom /cmd_vel
ros2 bag play my_teleop_bag
ros2 bag info my_teleop_bag


