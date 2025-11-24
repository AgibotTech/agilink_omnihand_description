# OmniHand ROS 2 Package

This is a ROS 2 package for **OmniHand**. It includes the URDF files for both the left and right hands, along with visualization support in RViz. The recommended ROS 2 distribution for using this package is **Humble**.

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
Build the workspace using:

```bash
colcon build
```

### 3. Source the Setup File
Before using the package, source the workspace setup file:

```bash
source install/setup.bash
```

## Generate OmniHand URDF File

To generate the URDF description from the Xacro files:

```bash
cd ~/omnihand_ws/src/omnihand_description/assets/urdf/xacro
xacro omnihand_right.xacro > omnihand_right.urdf
xacro omnihand_left.xacro > omnihand_left.urdf
```

## Visualization in RViz

### Right Hand
```bash
ros2 launch omnihand_description omnihand_description_launch.py
```

### Left Hand
```bash
ros2 launch omnihand_description omnihand_description_launch.py hand_type:=left
```

## MuJoCo MJCF Files

This package also provides **MuJoCo MJCF models** for simulating OmniHand in physics-based environments.  
The MJCF files are compatible with **MuJoCo 3.1.0 and later**.

Model files are located at:

```
omnihand_description/assets/MJCF/
```

This directory includes:

- `scene.xml` – A complete scene file for quick preview  
- `omnihand_left.xml` – Left-hand model  
- `omnihand_right.xml` – Right-hand model  
- `meshes/` – STL mesh assets used by MJCF  

### Quick Preview

To quickly preview the OmniHand model:

1. Open MuJoCo’s `simulate` viewer  
2. Drag and drop `assets/MJCF/scene.xml` into the window  
3. The OmniHand model will automatically load and display

Example:

![alt text](mujoco_image.png)

---

# OmniHand ROS 2 软件包

这是一个用于 **OmniHand** 的 ROS 2 软件包，包含左右手的 URDF 模型文件，并支持在 RViz 中可视化显示。推荐使用的 ROS 2 版本为 **Humble**。

## 安装指南

### 1. 克隆仓库

创建工作空间并克隆仓库：

```bash
mkdir -p ~/omnihand_ws/src
cd ~/omnihand_ws/src
git clone <repository_url>
cd ..
```

### 2. 编译工作空间

运行以下命令进行编译：

```bash
colcon build
```

### 3. 加载环境

在使用前，需要加载工作空间的环境配置：

```bash
source install/setup.bash
```

## 生成 OmniHand 的 URDF 文件

通过 Xacro 文件生成 URDF：

```bash
cd ~/omnihand_ws/src/omnihand_description/assets/urdf/xacro
xacro omnihand_right.xacro > omnihand_right.urdf
xacro omnihand_left.xacro > omnihand_left.urdf
```

## RViz 可视化

### 显示右手模型
```bash
ros2 launch omnihand_description omnihand_description_launch.py
```

### 显示左手模型
```bash
ros2 launch omnihand_description omnihand_description_launch.py hand_type:=left
```

## MuJoCo MJCF 文件

本包也提供 **MuJoCo MJCF 模型**，可用于在物理仿真环境中模拟 OmniHand。  
MJCF 文件兼容 **MuJoCo 3.1.0 及以上版本**。

模型路径：

```
omnihand_description/assets/MJCF/
```

包含以下内容：

- `scene.xml` – 完整场景文件，可快速预览  
- `omnihand_left.xml` – 左手 MJCF 模型  
- `omnihand_right.xml` – 右手 MJCF 模型  
- `meshes/` – 对应的 STL 网格文件  

### 快速预览方式

1. 打开 MuJoCo 自带的 `simulate` 查看器  
2. 将 `assets/MJCF/scene.xml` 拖入窗口  
3. 模型会自动加载并显示  

示例：

![alt text](mujoco_image.png)