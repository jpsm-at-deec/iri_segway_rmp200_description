# Description

The iri_segway_rmp200_description ROS package contains physical descriptions of the Segway RMP200 platform. The following files are provided:

 * Xacro macro to be included in higher level urdf or xacro files.

 * An example xacro file to be used as an example of use of the macro.

This package also includes launch files intended to simplify the use in
both the real and the simulated robot:

 * description.launch: loads the robot description with the appropiate model
and creates an instance of the robot_state_publisher ROS node. It has these
arguments:
 
    * node_name: (default: robot) base name given to the platform
related nodes.
 
    * model: (default: segway_example) name of the xacro file to include.
    
    * static_wheels: (default: false) publishes static transforms for wheel links, useful with the real robot when there is no joint information available

 * wheel_static_transform.launch: publishes static transforms, one for each
of the main wheels.

 * caster_wheels_static_transform.launch: publishes static transforms, one for each
of the caster supports and wheels.

 * test.launch: loads the description launch and shows the model in Rviz

# Dependencies

This node has the following dependencies:

  * [iri_diff_drive_gazebo](https://gitlab.iri.upc.edu/labrobotica/ros/platforms/iri_diff_drive_gazebo) (for simulation only)

  * robot_state_publisher

  * tf

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

The *segway_example.xacro* file shows an example of how to include the xacro 
macro in another xacro file.

The main xacro macro has the following parameters:

 * **name:** name of the robot used to specify the frames and joints to allow 
multiples instances.

 * **sim_config:** path and filename of the configuration file for the gazebo 
plugin. See the [iri_diff_drive_gazebo](https://gitlab.iri.upc.edu/labrobotica/ros/platforms/iri_diff_drive_gazebo)
documentation for a complete description of all the plugin parameters.