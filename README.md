# Winter School 2022 (www.fit.tsu.ru/robotics)


### Recommended Software (Links and instructions to the above mentioned software are given below):
1. Ubuntu 18.04
2. Robot Operating System(ROS) - Melodic
3. Ardupilot Repository
4. ardupilot_gazeebo repository
5. Git (sudo apt-get install git)
6. pymavlink (pip install pymavlink)
7. MAVROS
 
 

 #### Ubuntu 18.04
```
 https://releases.ubuntu.com/18.04/
```


 #### Robot Operating System(ROS) - Melodic
```
http://wiki.ros.org/melodic/Installation/Ubuntu
```
Install the ros melodic full desktop.

 #### MAVROS (optional)
```
https://github.com/mavlink/mavros/tree/master/mavros#installation
```



 #### Ardupilot Repository
```
git clone https://github.com/ArduPilot/ardupilot.git
cd ardupilot
git submodule update --init --recursive
Tools/environment_install/install-prereqs-ubuntu.sh -y
. ~/.profile
./waf configure --board CubeBlack
./waf copter
```

Reffer bellow for links, and troubleshooting guide :
1. https://ardupilot.org/dev/docs/building-setup-linux.html#building-setup-linux
2. https://github.com/ArduPilot/ardupilot/blob/master/BUILD.md
3. https://ardupilot.org/dev/docs/learning-ardupilot-the-example-sketches.html

 #### ardupilot_gazeebo repository
```
git clone https://github.com/SwiftGust/ardupilot_gazebo
cd ardupilot_gazebo
mkdir build
cd build
cmake ..
make -j4
sudo make install
```
Set Path of Gazebo Models / Worlds... Open up .bashrc
```
sudo gedit ~/.bashrc
```
Copy & Paste following at the end of .bashrc file 
*Use the correct path, will varry on the installation location*
```
source /usr/share/gazebo/setup.sh

export GAZEBO_MODEL_PATH=~/ardupilot_gazebo/models:${GAZEBO_MODEL_PATH}
export GAZEBO_MODEL_PATH=~/ardupilot_gazebo/models_gazebo:${GAZEBO_MODEL_PATH}
export GAZEBO_RESOURCE_PATH=~/ardupilot_gazebo/worlds:${GAZEBO_RESOURCE_PATH}
export GAZEBO_PLUGIN_PATH=~/ardupilot_gazebo/build:${GAZEBO_PLUGIN_PATH}

```
Install is complete



 #### То run the simulator - 
```
gnome-terminal -- bash -c "roscore"
gnome-terminal -- bash -c "sleep 5;rosrun gazebo_ros gazebo --verbose iris_ardupilot.world"
simvehicle.py -v ArduCoptor -f gazebo-iris -m --mav10 --console -IO
```


 #### Task  -  Use the qgroudcontrol groundstation to connect to the simulator and upload 4 waypoints to the flight navigation system and launch the mission. Record a video or take multiple screenshots and upload it to the given portal.

Reffer bellow for links, and troubleshooting guide :
1. https://github.com/SwiftGust/ardupilot_gazebo
2. https://ardupilot.org/dev/docs/sitl-simulator-software-in-the-loop.html
3. https://ardupilot.org/dev/docs/using-gazebo-simulator-with-sitl.html


