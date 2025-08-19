
 ### Robot Description (ROS 2 Humble)

This repository contains a simple **URDF model of a mobile robot** with two wheels and a chassis, along with the necessary launch files to visualize it in **RViz2**.  
It is part of a learning setup to understand URDF, robot_state_publisher, and RViz visualization.


### 1. Workspace & Package Setup

## Create a new workspace
```bash
mkdir -p ~/viz_ws/src
cd ~/viz_ws/src
````

## Create the package

```bash
ros2 pkg create --build-type ament_cmake robot_description
```


## 2. URDF Setup

Inside the package:

* Add a `urdf/` folder
* Place your URDF file (e.g., ` simple_mobile_robot.urdf`) inside it.


## 3. Launch File

Inside `launch/`, create a file `display.launch.py`:

* Loads the robot description from URDF
* Starts `robot_state_publisher`
* Starts `rviz2` with a config



## 4. Build & Source

```bash
cd ~/viz_ws
colcon build
source install/setup.bash
```


## 5. Running the Robot in RViz2

```bash
ros2 launch robot_description display.launch.py
```

### In RViz2:

1. Set **Fixed Frame** to `chassis`
2. Add **RobotModel** display
3. The robot will appear with wheels and chassis
4. Transforms are published by `robot_state_publisher` from the URDF


## Example Structure

```
viz_ws/
└── src/
    └── robot_description/
        ├── urdf/
        │   └── mobile_robot.urdf.xml
        ├── launch/
        │   └── display.launch.py
        ├── package.xml
        └── CMakeLists.txt
```

### Author

Created by **kimshy22** as part of learning **URDF and RViz2 visualization** in ROS 2 Humble.

````

