# Navigation system using Monodepth and PCL

<hr/>

## 1. Requirements

 [Github]
* Ubuntu : 16.04.6 LTS
* Python : 3.7.7 (But Default version is 3.5.2) 
* pip3 : 8.1.1 (python3.5)
* nvidia-driver : nvidia-384 
* cuda : 10.0.130 
* CUDNN : 7.65

 [Realsense D435]
* RealSense SDK 2.0 (librealsense version 2.34.0)
* Ubuntu : 16.04.6 LTS
* ROS kinetic
 
## 2. Setting_[Github]

### 2.1. nvidia-driver : nvidia-384
	sudo apt-get install nvidia-384

### 2.2 cuda 10.0 & CUDNN 7.65
	(Package List add)
	release="ubuntu"$(lsb_release -sr | sed -e "s/\.//g")
	echo $release
	sudo apt install sudo gnupg
	sudo apt-key adv --fetch-keys "http://developer.download.nvidia.com/compute/cuda/repos/"$release"/x86_64/7fa2af80.pub"
	sudo sh -c 'echo "deb http://developer.download.nvidia.com/compute/cuda/repos/'$release'/x86_64 /" > /etc/apt/sources.list.d/nvidia-cuda.list'
	sudo sh -c 'echo "deb http://developer.download.nvidia.com/compute/machine-learning/repos/'$release'/x86_64 /" > /etc/apt/sources.list.d/nvidia-machine-learning.list'
	sudo apt update
	sudo apt-get install cuda-10-0
	sudo apt-get install libcudnn7-dev

### PCL-Python install
	sudo add-apt-repository ppa:sweptlaser/python3-pcl #Python3 Only??
	sudo apt update
	sudo apt install python3-pcl
## 3. Setting_[Realsense D435]

### 3.1 librealsense 2.34.0
	sudo apt-key adv --keyserver keys.gnupg.net --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE || sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-key 
	sudo add-apt-repository "deb http://realsense-hw-public.s3.amazonaws.com/Debian/apt-repo xenial main" -u
	sudo apt-get install librealsense2-dkms
	sudo apt-get install librealsense2-utils
