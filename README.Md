## Useful commands
```
ros2 launch tomauto1_description display.launch.xml

ros2 launch base_4wd_bringup base_4wd.launch.xml
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
  [[launch_4wd]]
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
      command = bash -c "cd /home/daniel/projects/foodlikeair/baseline_4wd; ros2 launch base_4wd_bringup base_4wd.launch.xml; exec bash"
    [[[terminal2]]]
      type = Terminal
      parent = child1
      profile = default
      command = bash -c "cd /home/daniel/projects/foodlikeair/baseline_4wd; ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r /cmd_vel:=/diff_drive_controller/cmd_vel -p stamped:=true; exec bash"
[plugins]


``` 
