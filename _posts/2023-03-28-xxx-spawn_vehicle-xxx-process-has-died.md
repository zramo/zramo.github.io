---
layout: post
title: "[XXX/spawn_vehicle-XXX] process has died"
date: 2023-03-28 00:42:00 +0800
categories: ROS
---

# [XXX/spawn_vehicle-XXX] process has died

When problem like this occurs,

```bash
[XXX/spawn_vehicle-XXX] process has died [pid XXXXX, exit code 1, cmd /opt/ros/melodic/lib/gazebo_ros/spawn_model -urdf -param robot_description -model XXX __name:=spawn_vehicle __log:=~/.ros/log/XXXXXXXX/XXX-spawn_vehicle-XXX.log].
log file: ~/.ros/log/XXXXXXXX/XXX-spawn_vehicle-XXX.log
```

check the log file. If there is a error like this, probably the `sim_time` in the .world file is not set to 0 due to that it was once saved in gazebo.

```log
[rosout][INFO] YYYY-MM-DD hh:mm:ss,SSS: Spawn status: SpawnModel: Entity pushed to spawn queue, but spawn service timed out waiting for entity to appear in simulation under the name qz1
[rosout][ERROR] YYYY-MM-DD hh:mm:ss,SSS: Spawn service failed. Exiting.
```

Open the .world file, find `<sim_time>XXX</sim_time>` and change its value to `<sim_time>0</sim_time>`, the problem should be solved.

References:

[Spawn status: SpawnModel: Entity pushed to spawn queue, but spawn service timed out waiting for entity to appear in simulation under the name simple_arm · Issue #864 · ros-simulation/gazebo_ros_pkgs · GitHub](https://github.com/ros-simulation/gazebo_ros_pkgs/issues/864)
