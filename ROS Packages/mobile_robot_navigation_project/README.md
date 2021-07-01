# SOFAR Assignemt
## _Mobile Robot Navigation & Mapping_

This assignemt made by group Nav-05

| ID | Name |
| ------ | ------ |
| S4729321 | Mohamed Qaoud |
| S4844271 | Mohamed Mahmoud |
| S4927772 | Naresh Arthimalla |

## Aim of The Project
- Interact ROS with Unity.
- Localize and path planning for a mobile robot with an unknown environment for the robot in UNITY platform.
- Using LIDAR sensor on the robot "Husky Robot" to create a map in Rviz simulator.

## Software Components

The follwoing graph show the software components that has been used to implement this assignment.

x-special/nautilus-clipboard
copy
file:///home/alaaeldin/Downloads/Untitled%20Diagram%20(4).png
![Untitled Diagram (4)](https://user-images.githubusercontent.com/25705086/124192255-48d0fb80-dac5-11eb-9e33-ff1e75122d01.png)


## Installing

We tested the project in two different methods.

1 - Using the same machine (Linux) to implement the project.
2 - Using to different machines (Linux for ROS) (MacOS for Unity).

In order to install the system using the first method and run the code perfectly, we have to do the following:

1 - Install ROS-Noetic:
For all the instructions related the installation of ROS-Noetic, click the follwoing link: http://wiki.ros.org/noetic/Installation/Ubuntu

2 - Install Unity 2020.x.x

We used both Unity 2020.2.2/2020.3.13 You can download the desire Unity version from the following link: https://unity3d.com/get-unity/download/archive

3 - Clone our Repo into your ROS Workspace

By running this command in the Linux Terminal window 
```sh 
git clone https://github.com/mohammed-eldin/SOFAR_NAV_05
```
4 - Installing the Navigation and gmapping libraries by using the following commands:

Navigation library:
```sh 
sudo apt-get install ros-noetic-navigation 
```  
 Mapping library:
```sh
  sudo apt-get install ros-noetic-openslam-gmapping
```

5 - As the Husky robot is the robot that would scan the environment, we have to include it to our workspace:

In order to do so we have to clone the repo to our ROS workspace by using the following command 

```sh
git clone https://github.com/husky/husky.git
``` 

6 - Also, we have to install the LiDAR sensor by running the following command: 
```sh
sudo apt-get install ros-noetic-lms1xx
```

#####  The second method to prepare the system to run the project is as follows:
#

We follow the same procedures as the first method, but instead of using a same machine, we used two different machines “remotely” by using a middle ware to create a virtual network.

We used a application called LogMeIn Hamachi. After installing the application on both machines, one machine create a network and let the other machine join the created network. After joining the network, the application gives an IP address to each machine, so we use these IP addresses instead of the real ones in order to be on the same network “virtually”.

## Running The Code
After finishing all the required to install, we can run the project as follows:
##### In the ROS side:
#
1 - Launch the slam_gmapping node by the command:
```sh
roslaunch mobile_robot_navigation_project gmapping.launch
```
2 - Launch the move_base node by the command:
```sh
roslaunch mobile_robot_navigation_project move_base2.launch
```
3 - Launch the Rviz node by the command:
```sh
roslaunch mobile_robot_navigation_project view_model.launch
```
Also, uploading the model of the robot in the Rviz but opening it from Rviz from the repository config folder.

4 - Launch the Navigation node to start the communications between ROS and Unity by the following command line:
```
roslaunch mobile_robot_navigation_project navigation.launch
```

### In the Unity side
We have to open the already implemented environment and add the IP address of ROS machine into the Scene section in Unity. To avoid any errors, wait until launching all the nodes on the ROS side then press the play button in the Unity in the middle top window. If the connection is running correct, we would have a window that give us the date received from the ROS and the data sent by the Unity on a window on the left corner.

###### For more details about the components and the structure of the project, you can read the report.pdf file that exist in the repo.

x-special/nautilus-clipboard
copy
file:///home/alaaeldin/Downloads/211389299_502900794155848_7388450239768579561_n.png
![211389299_502900794155848_7388450239768579561_n](https://user-images.githubusercontent.com/25705086/124192489-a7967500-dac5-11eb-85f1-d43226fb7f79.png)


x-special/nautilus-clipboard
copy
file:///home/alaaeldin/Pictures/Screenshot%20from%202021-07-01%2019-18-25.png
![Screenshot from 2021-07-01 19-18-25](https://user-images.githubusercontent.com/25705086/124192372-7ddd4e00-dac5-11eb-89b2-f1517efe0dca.png)



