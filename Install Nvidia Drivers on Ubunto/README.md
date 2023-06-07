# Introduction
Nvidia graphics processing units (GPUs) used for gaming and professional use in offices. Nvidia GPUs used in data centers, visualization, automobile industry, and artificial intelligence. By default X.org X server use nouveau free/libre software drivers for nVidia cards. The nouveau driver generally provides the inferior performance to Nvidia’s proprietary graphics device drivers for gaming and other professional use. This page shows how to install Nvidia GPU drivers on an Ubuntu Linux desktop.
## Steps
The procedure to install proprietary Nvidia GPU Drivers on Ubuntu 16.04 / 17.10 / 18.04 / 18.10 / 20.04 / 22.04 LTS is as follows:
1. Update your system running apt-get command
2. You can install Nvidia drivers either using GUI or CLI method.
3. Open “Software and Updates” app to install install Nvidia driver using GUI OR Using CLI.
4. Reboot the computer/laptop to load the drivers.
5. Verify drivers are working

Let us see all commands and step-by-step instructions in details.

## Detailed Steps
### Note
Before Going to start installing anything, it is recommended to check the compatibility versions of [Tensorflow](https://www.tensorflow.org/install/source#gpu) and [Onnx](https://onnxruntime.ai/docs/execution-providers/CUDA-ExecutionProvider.html) to find out which versions suits best for your needs. 

##### Finding out information about your GPU by executing this command.
```sudo lshw -C display```

### Method # 1: Installing Nvidia driver using GUI on Ubuntu Linux
1. Go to search Bar and type "Software Updater" and Click on it.

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/ccbe360e-adf3-40aa-b02f-674332af4b0a)

2. Click on the `Settings...` Button.

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/1060987c-6c50-447f-abe5-0c4c0f1e671d)

3. Press on `Additional Drivers` Button.

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/e62c3bd5-9cf5-4a77-ab4b-622bd4161b50)

4. Choose nvidia-driver-470 (proprietary) and click on the Apply Changes button. You must authenticate yourself to install Nvidia driver on Ubuntu Linux.

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/f71348b0-1ec9-4444-8d72-cab82746e020)

5. Now wait for some time as Nvidia driver downloaded and installed from the internet

6. Click on the Close button when done. You must reboot Ubuntu Linux computer to use the driver by typing the following shutdown command:

```sudo shutdown -r now```

OR

```sudo reboot```
### Method # 2: Installing Nvidia driver using CLI on Ubuntu Linux
1. Execute the command as you must apply all pending security updates
```sudo apt update && sudo apt upgrade -y```
2. Then check the compatible version for your GPU from [NVIDIA Official](https://www.nvidia.com/Download/index.aspx?lang=en-us)
3. Then execute "sudo apt install nvidia-driver-xxx", in my case I'm on a 3060, so I should install nvidia-driver-470.
```sudo apt install nvidia-driver-xxx````
4. Then reboot or shutdown by typing the following shutdown command:

```sudo shutdown -r now```

OR

```sudo reboot```
### Verification Steps
Open the terminal application and type nvidia-smi to see GPU info and process that are using Nvidia GPU:
```nvidia-smi```
![image](https://github.com/Mr-MeerMoazzam/Cuda-Setup-In-Ubunto-22.04/assets/98279854/be8c6901-642a-4ece-a8b6-5a0c273830f6)
Now You have successfully installed NVIDIA GPU Drivers
