## Useful commands
```
ros2 launch tomauto1_description display.launch.xml

ros2 launch my_robot_bringup my_robot.launch.xml
ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r /cmd_vel:=/diff_drive_controller/cmd_vel -p stamped:=true
```
## Run terminator layout
```
terminator -l launch_ros
```

## ~/.config/terminator/config

```
[global_config]
  suppress_multiple_term_dialog = True
[keybindings]
[profiles]
  [[default]]
[layouts]
  [[default]]
    [[[window0]]]
      type = Window
      parent = ""
    [[[child1]]]
      type = Terminal
      parent = window0
  [[launch_ros]]
    [[[window0]]]
      type = Window
      parent = ""
    [[[child1]]]
      type = VPaned
      parent = window0
    [[[terminal1]]]
      type = Terminal
      parent = child1
      profile = default
      command = bash -c "cd /home/daniel/projects/foodlikeair/tomauto1; ros2 launch my_robot_bringup my_robot.launch.xml; exec bash"
    [[[terminal2]]]
      type = Terminal
      parent = child1
      profile = default
      command = bash -c "cd /home/daniel/projects/foodlikeair/tomauto1; ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r /cmd_vel:=/diff_drive_controller/cmd_vel -p stamped:=true; exec bash"
[plugins]


``` 
