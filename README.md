# OmniHand ROS 2 Package

This is a ROS 2 package for OmniHand. It includes the URDF files for both the left and right hands, as well as their visualization in RVIZ. The recommended ROS 2 version for installation is **Humble**.

## Installation

### 1. Clone the Repository
Create a new `src` directory, navigate into it, and clone the repository:

```bash
mkdir -p ~/omnihand_ws/src
cd ~/omnihand_ws/src
git clone <repository_url>
cd ..
```

### 2. Build the Package
Run the following command to build the package:

```bash
colcon build
```

### 3. Source the Setup File
After building, source the setup file to use the package:

```bash
source install/setup.bash
```

## Generate OmniHand URDF File
To generate the OmniHand URDF file from the Xacro description, use:

```bash
cd ~/omnihand_ws/src/omnihand_description/assets/urdf/xacro
xacro omnihand_right.xacro > omnihand_right.urdf
xacro omnihand_left.xacro > omnihand_left.urdf
```

## Visualization in RViz
To visualize OmniHand in RViz, run:

```bash
ros2 launch omnihand_description omnihand_description_launch.py
ros2 launch omnihand_description omnihand_description_launch.py hand_type:=left
```

