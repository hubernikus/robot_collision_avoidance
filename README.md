# Robot Collision Avoidance
This is a library for collision avoidance with (rigid) robots

---
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/ambv/black)

---
This package contains a dynamic obstacle avoidance algorithm for concave and convex obstacles as developped in [1] and [2].
---
Requirements: conda, jupyter notebook, python.

## Setup
To setup got to your install/code directory, and type:
```sh
git clone --recurse-submodules https://github.com/hubernikus/robot_collision_avoidance
```
(Make sure submodules are there if various_tools librarys is not installed.)

Go to file directory:
```sh
cd robot_collision_avoidance
``` 

## Custom Environment
Choose your favorite python-environment. I recommend to use [virtual environment venv](https://docs.python.org/3/library/venv.html).
Setup virtual environment (use whatever compatible environment manager that you have with Python >3.7).

``` bash
python3.10 -m venv .venv
```
with python -V > 3.7

Activate your environment
``` sh
source .venv/bin/activate
```

## Setup Dependencies
Install all requirements:
``` bash
pip install -r requirements.txt && pip install -e .
```

This module depends on the libraries [vartools](https://github.com/epfl-lasa/dynamic_obstacle_avoidance.git) and [dynamic_obstacle_avoidance](https://github.com/epfl-lasa/dynamic_obstacle_avoidance). Make sure that they re installed.

### Setup Simulator environment 
First make sure to include following scripts:
First, make sure to clone [aica-technology/docker-images](https://github.com/aica-technology/docker-images) and install the scripts before you start, as the instructions below rely on those scripts.
``` bash
bash scripts/install-aica-docker.sh
```

Then use the simulator, which can be found on:  
https://github.com/epfl-lasa/simulator-backend/tree/develop/pybullet_ros2


Spin up the container with

```console
aica-docker interactive aica-technology/ros2-simulator:galactic -u ros2
ros2 launch pybullet_ros2 franka.launch.py
```

Run the console with local-access:
``` bash
aica-docker interactive aica-technology/ros2-simulator:galactic -u ros2 --net host --no-hostname --ros-domain-id 0
```


