# Installation
This repository assumes that the [Robot Operating System (ROS)](https://www.ros.org/) has already been installed on your environment.
See [ros.org](https://www.ros.org/install/) to know how to install ROS. My environment is [here](#Enviroment).

<!-- このリポジトリを導入する環境では, すでに[ROS(Robot Operating System)](https://www.ros.org/)が導入されていることとします. ROSの導入方法は[ros.org](https://www.ros.org/install/)を参考にしてください. 私の[構築環境](#Environment)はこちらです. -->


## Create workspace
First, create the ROS workspace. The `<workspace>` can be named arbitrarily.
<!-- まずROSのワークスペースを生成します. `<workspace>`は任意の名前をつけてください. -->
```bash
## Create workspace for ROS, Change directory
$ mkdir -p workspace/src && cd workspace/src

## init workspace
$ catkin_init_workspace

## Make
$ cd ../
$ catkin_make
```

## Installation your environment
### Easy Installation
To clone `darknet` and `darknet_ros` as a submodule, you must clone them with `--recursive`. This allows you to clone the two submodules together.
<!-- `darknet`と`darknet_ros`をsubmoduleとして扱うためには, `--recursive`をつけて　cloneしてください.
これによりsubmoduleである2つのリポジトリをまとめてcloneすることができます. -->
```bash
$ cd src
$ git clone --recursive https://github.com/Tossy0423/yolov4-for-darknet_ros.git
```


<!-- ### If you don't use `darknet` and `darknet_ros` as a submodule
### `darknet`と`darknet_ros`をsubmoduleとして扱わずclone
To avoid using `darknet` and `darknet_ros` as submodules, you need to clone the two repositories separately.
`darknet`と`darknet_ros`をsubmoduleとして扱わないためには, ２つのリポジトリを別々にcloneする必要があります.
```bash
$ git clone https://github.com/Tossy0423/darknet.git
$ git clone https://github.com/Tossy0423/darknet_ros.git
```
In this case, the tree structure of the folder looks like this.
このやり方の場合, フォルダのツリー構造は以下のようになります.
```
src
├── darknet
│
├── darknet_ros
``` -->

## Download weights file
The weights file is very large and needs to be downloaded separately.
<!-- weightsはファイルサイズが大きので別でダウンロードする必要があります. -->
Download the weights file to `darknet_ros/darknet_ros/yolo_network_config/weights` to install it.
<!-- weightsファイルを導入する場所は, `darknet_ros/darknet_ros/yolo_network_config/weights`へダウンロードしてください. -->
```bash
$ wget https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights
```


## make pkg
```bash
# Change workspace directory
$ cd workspace

## Make
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
