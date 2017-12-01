[![Udacity - Robotics NanoDegree Program](https://s3-us-west-1.amazonaws.com/udacity-robotics/Extra+Images/RoboND_flag.png)](https://www.udacity.com/robotics)

# RoboND-EKFLab
Students will be able to drive the robot around in simulation and observe the `Odom` and `EKF` trajectories.  

### Steps to Launch the Simulation:
Launch the simulation in the VM machine provided in Term1. 

#### Step 1 Create a Catkin Workspace:
```sh
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/src
$ catkin_init_workspace
$ cd ..
$ catkin_make
```

#### Step 2 Perform a System Update:
```sh
$ sudo apt-get update
$ sudo apt-get install xterm
```

#### Step 3 Clone the Packages in src:
```sh
$ cd ~/catkin_ws/src
$ git clone https://github.com/udacity/RoboND-EKFLAB
$ cd RoboND-EKFLAB/
$ git clone https://github.com/turtlebot/turtlebot
$ git clone https://github.com/turtlebot/turtlebot_simulator
```

#### Step 4 Install Packages Dependancies:
```sh
$ cd ~/catkin_ws/
$ source devel/setup.bash
$ rosdep -i install turtlebot_gazebo
$ rosdep -i install turtlebot_teleop
```

#### Step 5 Build the Packages:
```sh
$ catkin_make
$ source devel/setup.bash
```

#### Step 6 Launch the Simulation:
```sh
$ cd ~/catkin_ws/src/RoboND-EKFLAB/
$ chmod +x ROSLaunch.sh
$ ./ROSLaunch.sh
```
Now, you should see Gazebo launching, multiple terminals, and rviz!

#### Step 7 Modify Rviz Settings:
1. Global Options - Fixed Frame - `base_footprint`
2. Grid - Reference Frame - `odom`
3. Add - By display type - `RobotModel` - ok
4. Add - By topic - /ekfpath - `Path` - Display Name - `EKFPath` - ok
5. Add - By topic - /odompath - `Path` - Display Name - `OdomPath` - ok
6. OdomPath - Color - `255;0;0`

### End Result:
Now, search for the keyboard terminal and drive the robot around. The `red` trajectory represents the `Odom path` whereas the `green` trajectory represents the `EKF path`.


![alt text](Outcome.png)





