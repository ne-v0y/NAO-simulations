# NAO-simulations
Package collections to run Gazebo simulation for NAO robot V6. 

### System parameters
- Ubuntu 18.04 LTS
- ROS Melodic

For ROS Kinectic and earlier, please use [official release](http://wiki.ros.org/nao). 

### Getting started
1. Follow the [install guide](http://doc.aldebaran.com/2-5/dev/cpp/install_guide.html) to download and install NAOqi SDK. Make sure your worktree contains location you are going to clone this repository.
2. Follow the [ROS Setup Guide](http://wiki.ros.org/melodic/Installation/Ubuntu) for installing Melodic. **Desktop-Full** version is highly recommended.   
3. Set up this repository after cloning,
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
Find NAO specs [here](http://doc.aldebaran.com/2-8/family/nao_technical/lola/actuator_sensor_names.html).
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
- [nao_moveit_config](https://github.com/ros-naoqi/nao_moveit_config)
- [naoqi_bridge](https://github.com/ros-naoqi/naoqi_bridge)
- [naoqi_bridge_msg](https://github.com/ros-naoqi/naoqi_bridge_msgs)

Created modules
- [nao_meshes](https://github.com/ros-naoqi/nao_meshes/issues/6), with NAO [V6 urdf](http://doc.aldebaran.com/2-8/family/nao_technical/kinematics_naov6.html). 

### TODO
- [ ] Create xacros for V6 model
- [ ] Get NAOqi simulation to work