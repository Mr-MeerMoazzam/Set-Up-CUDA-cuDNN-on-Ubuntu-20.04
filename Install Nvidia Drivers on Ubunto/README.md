# Introduction
Nvidia graphics processing units (GPUs) used for gaming and professional use in offices. Nvidia GPUs used in data centers, visualization, automobile industry, and artificial intelligence. By default X.org X server use nouveau free/libre software drivers for nVidia cards. The nouveau driver generally provides the inferior performance to Nvidia’s proprietary graphics device drivers for gaming and other professional use. This page shows how to install Nvidia GPU drivers on an Ubuntu Linux desktop.
## Steps
The procedure to install proprietary Nvidia GPU Drivers on Ubuntu 16.04 / 17.10 / 18.04 / 18.10 / 20.04 / 22.04 LTS is as follows:
1. Update your system running apt-get command
2. You can install Nvidia drivers either using GUI or CLI method.
3. Open “Software and Updates” app to install install Nvidia driver using GUI OR type “sudo apt install nvidia-driver-525 nvidia-dkms-525” at the CLI.
4. Reboot the computer/laptop to load the drivers.
5. Verify drivers are working

Let us see all commands and step-by-step instructions in details.

## Detailed Steps
1. Finding out information about your GPU by executing this command.
'''sudo lshw -C display'''
### Method # 1 : Installing Nvidia driver using GUI on Ubuntu Linux
1. Go to search Bar and type "Software Updater"
![image](https://github.com/Mr-MeerMoazzam/Cuda-Setup-In-Ubunto-22.04/assets/98279854/d883cf18-e356-4f27-b196-c84eff800222)
