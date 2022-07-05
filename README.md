# Installation
This repository assumes that the [Robot Operating System (ROS)](https://www.ros.org/) has already been installed on your environment.
See [ros.org](https://www.ros.org/install/) to know how to install ROS.

## Create workspace
First, create the ROS workspace. The `<workspace>` can be named arbitrarily.
```bash
## Create workspace for ROS, Change directory
$ mkdir -p <workspace>/src && cd <workspace>/src

## init workspace
$ catkin_init_workspace

## Make
$ cd ../
$ catkin_make
```

## Installation your environment
### Easy Installation
To clone `darknet` and `darknet_ros` as a submodule, you must clone them with `--recursive`. This allows you to clone the two submodules together.
```bash
$ cd src
$ git clone --recursive https://github.com/Tossy0423/yolov4-for-darknet_ros.git
```

## Download weights file
The weights file is very large and needs to be downloaded separately.
Download the weights file to `darknet_ros/darknet_ros/yolo_network_config/weights` to install it.
```bash
$ wget https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights
```


## make pkg
Edit CMakeLists.txt file at 'darknet_ros/darknet_ros'
Match CUDA arch and your NVIDIA driver at [here](https://arnon.dk/matching-sm-architectures-arch-and-gencode-for-various-nvidia-cards/)
like this "gencode arch=compute_75,code=[sm_75,compute_75]"

```bash
$ cd <workspace>
$ catkin_make

# Write source command in ~/.bashrc
$ echo "source ~/workspace/devel/setup.bash" >> ~/.bashrc
```


# Environment

|         Topics         	|                     Spec                     	|
|:----------------------:	|:--------------------------------------------:	|
|          Model         	|              Dell ALIENWARE m15              	|
|           CPU          	|   Intel® Core™ i7-8750H CPU @ 2.20GHz × 12   	|
|           GPU          	| GeForce RTX 2070 with Max-Q Design/PCIe/SSE2 	|
|           RAM          	|                    15.4 GB                   	|
|           OS           	|           Ubuntu 18.04.3 LTS bionic          	|
|       Midlleware       	|                  ROS Melodic                 	|
|       NVIDIA-SMI       	|                    440.100                   	|
|     Driver Version     	|                    440.100                   	|
|      CUDA Version      	|                     10.2                     	|
| Cuda compilation tools 	|            release 10.1, V10.1.243           	|
