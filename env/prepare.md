1. On Windows 10, install the WSL if you don’t have it. Follow the instructions here: https://docs.microsoft.com/en-us/windows/wsl/install-win10Links to an external site.
install wsl in win10
https://learn.microsoft.com/en-us/windows/wsl/install
https://learn.microsoft.com/en-us/windows/wsl/install-on-server

wsl --install

以管理员身份打开 windows PowerShell 并运行：
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux

2. Once you have that installed, you can download and install MobaXterm (which is the enhanced terminal with graphical capacity): https://mobaxterm.mobatek.netLinks to an external site.
It is recommended that you INSTALL the program and not use the portable version.

3. Inside MobaXterm, you will probably will see that your WSL is already listed on the left panel as an available connection. Just double-click it and you will be accessing it via MobaXterm. If by any chance you don’t see it there, close MobaXterm and go to the WSL terminal, because probably the WSL is not allowing SSH connections. You can follow this linkLinks to an external site. for the instructions on how to do it. You need to complete until the step Start or restart the SSH service, while the further steps are optional, but might be useful.

4. install conda
  
download:
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

install:
cd ~/Downloads
sh Miniconda3-latest-Linux-x86_64.sh

install mamba
conda init
conda install -n base -c conda-forge mamba

5. Inside MobaXterm, type the commands below to install the X-server graphical packages that will be used to launch RStudio. https://docs.anaconda.com/anaconda/install/linux/Links to an external site.
sudo apt-get update
sudo apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6

6. Create a conda environment from file

download environment.yaml:
curl -o nn_dl_python.yaml https://raw.githubusercontent.com/NBISweden/workshop-neural-nets-and-deep-learning/master/common_assets/conda_envs/nn_dl_python.yaml

build env:
mamba env create -f nn_dl_python.yaml

7. Activate the environment
conda activate nn_dl_python

test file
curl -LJ -o introduction_to_keras_1.ipynb https://github.com/NBISweden/workshop-neural-nets-and-deep-learning/raw/master/session_annBuildingBlocks/lab_keras/introduction_to_keras_1.ipynb

jupyter-notebook



