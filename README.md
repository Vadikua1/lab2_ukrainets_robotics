# 🤖 Lab 2: Introduction to ROS2 and Simulation Environment


## 🛠 Prerequisites

- Docker Desktop
- WSL
- Native Ubuntu
- DualBoot

---

## 🚀 Getting Started

### 1️⃣ Environment Setup

Clone the repository and navigate to the project folder:

```bash
git clone https://github.com/Vadikua1/lab2_ukrainets_robotics.git
cd lab2_ukrainets_robotics
```
### 2️⃣ Docker Image Build & Run

Build the Docker image
(Required for the first run or after Dockerfile changes):
```bash
./scripts/cmd build-docker
```
### Start the container:
```bash
./scripts/cmd run
```

### 3️⃣ ROS2 Workspace Build

Inside the container, compile your package:
```bash
cd /opt/ws
colcon build --packages-select lab2
source install/setup.bash
```
## 🎮 Running the Lab
### ▶️ Step 1: Main Launch

Launch the simulation environment:
```bash
ros2 launch lab2 gazebo_ros2.launch.py
```
This command starts:

Gazebo

RViz2

Communication bridge

In the Gazebo window, you MUST click the Play button (orange triangle at the bottom left) to start the simulation physics.

### 🤖 Step 2: Robot Controller (Movement)

Open a new terminal window and enter the container:
```bash
docker exec -it robotics_intro bash

```
Then run:
```bash
source /opt/ros/jazzy/setup.bash
source /opt/ws/install/setup.bash
ros2 run lab2 robot_controller
```
The robot will start moving in a sinusoidal (wavy) pattern.

### 📡 Step 3: LiDAR Processor (Subscriber)

In another new terminal, run:
```bash
ros2 run lab2 lidar_subscriber
```
The console will display real-time statistics of distances to obstacles.
