## Build

```
source /opt/ros/noetic/setup.bash
catkin_make --only-pkg-with-deps industrial_msgs industrial_utils industrial_robot_simulator aubo_i5_moveit_config aubo_driver aubo_controller
```

## Usage
### Simulator
If you want to connect to real robot, follow the step 1 to 5 below.
1. ros1 master
````
source /opt/ros/noetic/setup.bash
roscore
````

2. action_bridge
   
```
ros2 run action_bridge action_bridge_follow_joint_trajectory_2_1 aubo_i5_controller
```

3. ros1_bridge
   
```
ros2 run ros1_bridge dynamic_bridge
```

4. aubo_ros1_control

```
roslaunch aubo_i5_moveit_config moveit_planning_execution.launch
```

5. aubo_ros2_moveit2 

```
ros2 launch run_move_group auboi5_moveit.launch.py
```