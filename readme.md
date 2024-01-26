## Project: Neural Nets and Deep Learning

[**Github Project**](https://github.com/NBISweden/workshop-neural-nets-and-deep-learning/tree/master/session_annBuildingBlocks/lab_keras)

[**Documents**](https://uppsala.instructure.com/courses/93000/pages/what-you-as-student-need-to-do-before-the-course-starts)


### 1. Install wsl in windows

#### 1.1 wsl install

On Windows 10, install the WSL if you don’t have it. Follow the instructions here: 

https://docs.microsoft.com/en-us/windows/wsl/install-win10

https://learn.microsoft.com/en-us/windows/wsl/install

```shell
wsl --install
```

#### 1.2 windows10+ permission

https://learn.microsoft.com/en-us/windows/wsl/install-on-server

以管理员身份打开 windows PowerShell 并运行：

```shell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

### 2. MobaXterm

#### 2.1 Install
Download and install MobaXterm (which is the enhanced terminal with graphical capacity): https://mobaxterm.mobatek.netLinks to an external site.

It is recommended that you INSTALL the program and not use the portable version.

#### 2.2 SSH service

Inside MobaXterm, you will probably will see that your WSL is already listed on the left panel as an available connection. 

If by any chance you don’t see it there, close MobaXterm and go to the WSL terminal, because probably the WSL is not allowing SSH connections. 

You can follow this [link](https://www.illuminiastudios.com/dev-diaries/ssh-on-windows-subsystem-for-linux/) for the instructions on how to do it. You need to complete until the step:

```shell
Start or restart the SSH service
```

 while the further steps are optional, but might be useful.

### 3. Install conda in liunx
  
download:
```shell
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

install:
```shell
cd ~/Downloads
sh Miniconda3-latest-Linux-x86_64.sh
```

install mamba
``` shell
conda init
conda install -n base -c conda-forge mamba
```

### 4. Graphical packages for RStudio

Inside MobaXterm terminal, type the commands below to install the X-server graphical packages that will be used to launch RStudio. 

https://docs.anaconda.com/anaconda/install/linux/

```shell
sudo apt-get update
sudo apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6
```

### 5. Create a conda environment from file

download environment.yaml:
```shell
curl -o nn_dl_python.yaml https://raw.githubusercontent.com/NBISweden/workshop-neural-nets-and-deep-learning/master/common_assets/conda_envs/nn_dl_python.yaml
```

build env:
```shell
mamba env create -f nn_dl_python.yaml
```

### 6. Activate environment
```shell
conda activate nn_dl_python
```

### 7. test file
```shell
curl -LJ -o introduction_to_keras_1.ipynb https://github.com/NBISweden/workshop-neural-nets-and-deep-learning/raw/master/session_annBuildingBlocks/lab_keras/introduction_to_keras_1.ipynb

jupyter-notebook
```
