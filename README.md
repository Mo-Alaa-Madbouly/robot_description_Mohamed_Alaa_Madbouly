# robot_description_Mohamed_Alaa_Madbouly
ROS2 Arabic - Assignment 4


# Robot Description

A ROS 2 package containing a custom robot model created using URDF/Xacro.

The robot model includes:
- Mobile robot chassis
- Two drive wheels
- Rear caster wheel
- RPLIDAR sensor
- ZED camera
- Visual, collision, and inertial properties

## Package Structure

```text
robot_description/
├── urdf/
│   └── robot_description.urdf.xacro
├── meshes/
│   ├── lidar.STL
│   └── zed.stl
├── CMakeLists.txt
└── package.xml
```

## Create the Workspace

```bash
mkdir -p ~/robot_description_ws/src
cd ~/robot_description_ws
colcon build
source install/setup.bash
```

## Build the Package

```bash
cd ~/robot_description_ws
colcon build
source install/setup.bash
```

## Robot Description

The main robot model is defined in:

```text
robot_description/urdf/robot_description.urdf.xacro
```

The Xacro file defines the robot links, joints, wheels, caster, LiDAR, camera, materials, collision geometry, and inertial properties.

The LiDAR and camera mesh files are stored in:

```text
robot_description/meshes/
```

## Preview the Robot

Convert the Xacro file to URDF:

```bash
ros2 run xacro xacro ~/robot_description_ws/src/robot_description/urdf/robot_description.urdf.xacro
```

To save the generated URDF:

```bash
ros2 run xacro xacro ~/robot_description_ws/src/robot_description/urdf/robot_description.urdf.xacro > robot.urdf
```

The generated URDF can then be opened in a URDF visualizer such as RViz.

## Verify the Package

```bash
ros2 pkg list | grep robot_description
```

## Expected Result

The robot model should appear with its chassis, two wheels, rear caster wheel, LiDAR, and ZED camera.

Make sure the mesh files are present in the `meshes` folder before previewing the robot.
