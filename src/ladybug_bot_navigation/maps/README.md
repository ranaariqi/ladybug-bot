# Maps

This folder is where `map_saver` output goes. It's empty until you generate a map.

## Generate the map (once)

```bash
roslaunch ladybug_bot_gazebo ladybug_bot_world.launch
roslaunch ladybug_bot_navigation gmapping_demo.launch
roslaunch ladybug_bot_teleop keyboard_teleop.launch
```

Drive the robot around the whole room in RViz/Gazebo until the map looks complete,
then in a new terminal:

```bash
rosrun map_server map_saver -f $(rospack find ladybug_bot_navigation)/maps/hotel_room
```

That creates `hotel_room.yaml` and `hotel_room.pgm` right here, which
`amcl_demo.launch` and `navigation.launch` both expect by default.
