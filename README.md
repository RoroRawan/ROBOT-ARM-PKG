# ROBOT-ARM-PKG

__________________________________________________________________

As i mention at a previous repository called "install-ROS-1-and-ROS-2
" specially at this file "How can I install ROS 1 on Ubuntu" here is the link:

https://github.com/RoroRawan/install-ROS-1-and-ROS-2 what I did is I installed ubuntu through windows powershell via WSLg and after that I installed ROS 1 on it, so not as virtualbox ubuntu version؛ all the file going to installed directelly. what I’m saying is that we have to install linux(file) to downlaod on it all the backages that we need, a long further to do this
#### we are going to:

* "open the ubuntu"
* "type in this cmd:

```
sudo apt install nautilus -y
```

* "go to start icon then all app after that
search on file(linux)

#### now install all the dependence:

```
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential

sudo apt install python3-rosdep

sudo rosdep init

rosdep update

mkdir -p ~/catkin_ws/src

cd ~/catkin_ws/

catkin_make

cd ~/catkin_ws/src

git clone https://github.com/smart-methods/arduino_robot_arm.git 

cd ~/catkin_ws
```
```
rosdep install --from-paths src --ignore-src -r -y

sudo apt-get install ros-noetic-moveit

sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui

sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher

sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control

catkin_make
```

* to install Arduino IDE:
```
sudo apt update
mkdir arduino
cd arduino/
wget https://downloads.arduino.cc/arduino-1.8.15-linux64.tar.xz
```
   to extract the tar.xz file:
```
tar -xvf ./arduino-1.8.15-linux64.tar.xz
cd arduino-1.8.15/
sudo ./install.sh
```
* to avoid any possible problems when using Arduino IDE, add your system user to the dialout group.

This is the procedure to access the serial port from the Arduino Software (IDE) if you get an error.

It might happen that when you upload a sketch you get the following error:

"Error opening serial port ..." 

If you get this error, you need to set serial port permissions.

Type the following command in the terminal:

```
ls -l /dev/ttyACM*
```
* you will get something like:

crw-rw---- 1 root dialout 188, 0 5 apr 23.01 ttyACM0

the data we need is "dialout" (it is the group owner of the file).

Now we just need to add our system user to the group:
```
sudo usermod -a -G dialout <username>
```
where <username> is your Linux user name. You will need to log out and in again for this to take effect.
