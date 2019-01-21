# NAO-simulations
Package collections to run simulation for NAO robot V6. 

### System parameters
- Ubuntu 18.04 LTS
- ROS Melodic

For ROS Kinectic and earlier, please use [official release](http://wiki.ros.org/nao). 

### Getting started
Follow the [ROS Setup Guide](http://wiki.ros.org/melodic/Installation/Ubuntu) for installing Melodic. **Desktop-Full** version is highly recommended.   
To set up this repository,
```bash
sudo apt-get update
cd NAO-simulation/catkin_ws
# This downloads dependencies used by packages in this workspace
rosdep install --from-paths src --ignore-src -r -y --rosdistro melodic

# After download is completed, build the packages
catkin_make

# (Optional) Overlay environment of this workspace in .bashrc
PATH=$(pwd -P) && echo "source $PATH/devel/setup.bash" >> ~/.bashrc 
source $HOME/.bashrc
``` 

To launch simulation in Gazebo,
```bash
roslaunch nao_gazebo_plugin nao_gazebo.launch
```

To launch motion planner in Rviz,
```bash
roslaunch nao_moveit_config moveit_planner.launch
```

### Available controllers
All joints are covered, comparing with information provided on [NAO specs](http://doc.aldebaran.com/2-8/family/nao_technical/lola/actuator_sensor_names.html).
- Head
- Left/Right Arm
- Left/Right Foot
- Left/Right Hand
- Left/Right Leg
- Pelvis
- FSR Left/Right Foot
- Camera top/bottom
- Sonar Left/Right


### Modules
Submodules
- [nao_robot](https://github.com/ros-naoqi/nao_robot)
- [nao_extras](https://github.com/ros-naoqi/nao_extras)
- [nao_virtual](https://github.com/ros-naoqi/nao_virtual)
- [naoqi_bridge_msg](https://github.com/ros-naoqi/naoqi_bridge_msgs)
- [nao_moveit_config](https://github.com/ros-naoqi/nao_moveit_config)

Created modules
- [nao_meshes](https://github.com/ros-naoqi/nao_meshes/issues/6), with NAO [V6 urdf](http://doc.aldebaran.com/2-8/family/nao_technical/kinematics_naov6.html). 
 