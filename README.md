# Description

This ROS package contains physical descriptions of the SegwayRMP200 platform.

# Dependencies

This node has the following dependencies:

  * [iri_diff_drive_gazebo](https://gitlab.iri.upc.edu/labrobotica/ros/platforms/iri_diff_drive_gazebo) (for simulation only)
  * [robot_state_publisher](http://wiki.ros.org/robot_state_publisher)
  * [xacro](http://wiki.ros.org/xacro)
  * [tf](http://wiki.ros.org/tf)

# Install

This package, as well as all IRI dependencies, can be installed by cloning the
repository inside the active workspace:

```
roscd
cd ../src
git clone https://gitlab.iri.upc.edu/labrobotica/ros/platforms/segway/iri_segway_rmp200_description.git 
```

However, this package is normally used as part of a wider installation (i.e. a
robot, an experiment or a demosntration) which will normally include a complete
rosinstall file to be used with the [wstool](http://wiki.ros.org/wstool) tool.

# How to use it

The following files are provided:

 * segway_example.xacro: an example xacro file of how to include the xacro 
macro.
 
 * segway.xacro: xacro macro to be included in higher level urdf or xacro files.
 
  ** name: name of the robot used to specify the frames and joints to allow 
multiples instances.

  ** sim_config: path and filename of the configuration file for the gazebo 
plugin. See the [iri_diff_drive_gazebo](https://gitlab.iri.upc.edu/labrobotica/ros/platforms/iri_diff_drive_gazebo)
documentation for a complete description of all the parameters.

This package also includes two launch files intended to simplify the use
both the real and the simulated robot:

 * description.launch: loads the robot description with the appropiate model
and creates an instance of the robot_state_publisher ROS node. It has these
arguments:
 
  ** ns: (default: segway) base name given to the platform
related nodes.
 
  ** model: (default: segway_example) name of the xacro file to include.

  ** static_wheels: (default: false) enables launching static transforms for wheel joints

 * wheel_static_transf.launch: publishes four static transforms, one for each
of the wheels.