# Introduction
Nvidia graphics processing units (GPUs) used for gaming and professional use in offices. Nvidia GPUs used in data centers, visualization, automobile industry, and artificial intelligence. By default X.org X server use nouveau free/libre software drivers for nVidia cards. The nouveau driver generally provides the inferior performance to Nvidia’s proprietary graphics device drivers for gaming and other professional use. This page shows how to install Nvidia GPU drivers on an Ubuntu Linux desktop.
## Steps
The procedure to install proprietary Nvidia GPU Drivers on Ubuntu 16.04 / 17.10 / 18.04 / 18.10 / 20.04 / 22.04 LTS is as follows:
1. Update your system running apt-get command
2. You can install Nvidia drivers either using GUI or CLI method.
3. Open “Software and Updates” app to install install Nvidia driver using GUI.
4. Reboot the computer/laptop to load the drivers.
5. Verify drivers are working

Let us see all commands and step-by-step instructions in details.

## Detailed Steps
1. Finding out information about your GPU by executing this command.
'''sudo lshw -C display'''
### Installing Nvidia driver using GUI on Ubuntu Linux
1. Go to search Bar and type "Software Updater" and Click on it.
![image](https://github.com/Mr-MeerMoazzam/Cuda-Setup-In-Ubunto-22.04/assets/98279854/d883cf18-e356-4f27-b196-c84eff800222)
2. Click on the `Settings...` Button.
![image](https://github.com/Mr-MeerMoazzam/Cuda-Setup-In-Ubunto-22.04/assets/98279854/34fc4a33-863b-4f1f-8e4e-3eeffcac3cfd)
3. Press on `Additional Drivers` Button.
![image](https://github.com/Mr-MeerMoazzam/Cuda-Setup-In-Ubunto-22.04/assets/98279854/4b0dc388-eb06-4734-9193-a6674ffc083f)
4. Choose nvidia-driver-530 (proprietary, tested) and click on the Apply Changes button. You must authenticate yourself to install Nvidia driver on Ubuntu Linux.
![image](https://github.com/Mr-MeerMoazzam/Cuda-Setup-In-Ubunto-22.04/assets/98279854/629d5753-8e2a-47fd-a95f-c1dfe37bf0d1)
5. Now wait for some time as Nvidia driver downloaded and installed from the internet
![image](https://github.com/Mr-MeerMoazzam/Cuda-Setup-In-Ubunto-22.04/assets/98279854/553bbe3e-ed81-48c2-893d-37517f01f8b8)
6. Click on the Close button when done. You must reboot Ubuntu Linux computer to use the driver by typing the following shutdown command:
 '''sudo shutdown -r now'''
 OR
 '''sudo reboot'''
### Verification Steps
