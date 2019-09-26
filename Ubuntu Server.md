# Set Up a Ubuntu Server for Deep Learning

## Preparation 
  1. Download Ubuntu 18.04 LTS. The Server and Desktop editions of Ubuntu are almost identical, with the notable exception of the visual interface (called X) not being installed with Server. Since the workstation is used for the group, I installed the Server version.
  
  2. Create a [bootable USB drive](https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-windows#1).
  
## Install
  1. Disable the Secure Boot from BIOS (F12)
  2. Plug USB drive, reboot machine (F12), and start installation, reboot.
  3. Remote access via SHH (MobaXterm for Windows)
  4. set up passward for root user:
      

## Deep learning environment
From here, all operations are done on my Windows workstation via SSH (MobaXterm)

First, install some basics.
```
sudo apt-get update
sudo apt-get --assume-yes upgrade
sudo apt-get --assume-yes install tmux build-essential gcc g++ make binutils
sudo apt-get --assume-yes install software-properties-common
sudo apt-get --assume-yes install git
```



  **Install Nvidia Drivers**
  
  ```
  sudo add-apt-repository ppa:graphics-drivers/ppa
  sudo apt-get update
  sudo apt-get install nvidia-driver-418
  ```
  You need to reboot the workstation to finish the installation.
  ```
  sudo reboot now
  ```
  
  
  
  After reboot the machine, check the driver.
  
  ```
  nvidia-smi
  ```
  
  Here we don't need to install **cudnn** and **Cuda** because when use conda to install pytorch, it will include the necessary cuda and cudnn binaries.
  
  **Install anaconda**
  
Download [anaconda](https://www.anaconda.com/) 

Install follow this [blog](https://www.digitalocean.com/community/tutorials/how-to-install-anaconda-on-ubuntu-18-04-quickstart)

 ## Set Up Conda Enviroment
 
 **Create** a conda enviroment. You can change **avengers** to your prefer name.
 ```
 conda create --name avengers
 ```
 
And **activate** the enviroment.
```
source avtivate avengers
```

Install [pytorch](https://pytorch.org/)

```
conda install pytorch torchvision cudatoolkit=10.0 -c pytorch
```
  
Install some packages

```
conda install -c rdkit rdkit
conda install scikit-learn 
conda install -c conda-forge matplotlib
conda install notebook ipykernel 
conda install jupyter

```
  
## TO DO. SETUP SSH  
  
