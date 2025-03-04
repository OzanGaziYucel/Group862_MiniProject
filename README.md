# Group862_MiniProject
This repository contains a ROS2-based Gazebo simulation environment for the mini project of ROB8-Group 862 of Aalborg University, Spring 2025. Follow the guide below to install the necessary dependencies, set up the workspace, and launch the simulation.

-----------------------------------------------------------------------------------------------------------------------------------------------
## 1. System Requirements<br>
#### ✅ OS: Ubuntu 22.04 (Recommended for ROS2 Humble) <br>
#### ✅ ROS2 Distribution: Humble <br>
#### ✅ Gazebo Version: Fortress (or compatible)
-----------------------------------------------------------------------------------------------------------------------------------------------
## 2. Installation<br>
### 2.1 Install ROS2 Humble<br>
Update system packages:
```
sudo apt update && sudo apt upgrade -y
```
Install ROS2 Humble Desktop:
```
sudo apt install -y ros-humble-desktop
```
Add ROS2 to the environment:
```
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
### 2.2 Install Gazebo<br>
Install Gazebo Fortress:
```
sudo apt install -y ros-humble-gazebo-ros-pkgs
```
Verify Gazebo installation:
```
gazebo
```
If Gazebo opens, the installation is successful.<br>
### 2.3 Install Additional Dependencies
```
sudo apt install -y python3-pip
pip install catkin_pkg
```
-----------------------------------------------------------------------------------------------------------------------------------------------
## 3. Clone and Set Up the Repository<br>
### 3.1 Clone the GitHub Repository
```
cd ~
git clone https://github.com/OzanGaziYucel/Group862_MiniProject.git
```
### 3.2 Build the ROS2 Workspace<br>
Navigate to the project folder:
```
cd group862_mini_project
```
Build the ROS2 package:
```
colcon build --symlink-install
```
Source the workspace:
```
source install/setup.bash
```
-----------------------------------------------------------------------------------------------------------------------------------------------
## 4. Configure Gazebo to Load Models<br>
To make sure Gazebo can find the required models, set up the model path:
```
export GAZEBO_MODEL_PATH=~/.gazebo/models:$GAZEBO_MODEL_PATH
```
To make this permanent:
```
echo 'export GAZEBO_MODEL_PATH=~/.gazebo/models:$GAZEBO_MODEL_PATH' >> ~/.bashrc
source ~/.bashrc
```
-----------------------------------------------------------------------------------------------------------------------------------------------
## 5. Build and Source<br>
After making changes to any nodes, you must rebuild and source the workspace before running the simulation.
```
cd ~/group862_mini_project
source /opt/ros/humble/setup.bash
colcon build --symlink-install
source ~/group862_mini_project/install/setup.bash
```
-----------------------------------------------------------------------------------------------------------------------------------------------
## 6. Running the Simulation<br>
In all new terminals, you must source ROS2 and the package before launching anything. Otherwise, commands like ros2 launch won’t work.
```
cd ~/group862_mini_project
source /opt/ros/humble/setup.bash
source ~/group862_mini_project/install/setup.bash
```
Launching the Simulation
```
ros2 launch mp_862 launch_mp_862.py
```
