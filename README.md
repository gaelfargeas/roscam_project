# Roscam Project

# What is this?
Roscam is a projet using ros, QT and tensorflow.

![](https://raw.githubusercontent.com/gaelfargeas/roscam_project/main/img/roscam.png)
# Requirements

python >= 3.5

# install

1) install package 

```sh
sudo apt install qttools5-dev-tools libqt5svg5-dev qtmultimedia5-dev libqt5websockets5-dev python3 git
pip3 install tensorflow

sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
sudo apt update
sudo apt install ros-noetic-desktop-full ros-noetic-catkin
echo "source /opt/ros/indigo/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

2) create catkin workspace

```sh
cd ~ && mkdir roscam && cd roscam
mkdir src && cd src

catkin_init_workspace
```

clone project package packages

- roscam_sensors

```sh
git clone https://github.com/gaelfargeas/roscam_sensors.git
```

- roscam_tensorflow2

```sh
git clone https://github.com/gaelfargeas/roscam_tensorflow2.git
```

- roscam_application

```sh
git clone https://github.com/gaelfargeas/roscam_application.git
```
go back to catkin workspace

```sh
cd ../
catkin_make
source devel/setup.bash
catkin_make
```



# How to use

you will need multiple command prompt
run ros packages

## first command prompt :

go to catkin workspace and source if its not already done.

```sh
cd ~/roscam
source devel/setup.bash
```

start ros server.

```sh
roscore
```

## others command prompt:

go to catkin workspace and source if its not already done.

```sh
cd ~/roscam
source devel/setup.bash
```
run packages. usually it's 1 command prompt per package.

```sh
rosrun roscam_sensors main.py

rosrun roscam_tensorflow2 main.py

rosrun roscam_application roscam_application
```

you can ralso run all package in the same command prompt.

```sh
rosrun roscam_sensors main.py && rosrun roscam_tensorflow2 main.py && rosrun roscam_application roscam_application
```
