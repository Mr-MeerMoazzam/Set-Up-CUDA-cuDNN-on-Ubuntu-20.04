# Cuda-Setup-In-Ubunto-22.04
In this repo, we will show you how to install CUDA on Ubuntu 22.04 LTS from the official package repository of Ubuntu. We will also show you how to write, compile, and run your very first CUDA program on Ubuntu 22.04 LTS as well.
## Cuda
The full form of CUDA is Compute Unified Device Architecture. CUDA is a parallel computing platform and programming model developed by NVIDIA. It is used to run the programs on NVIDIA Graphics Processing Units (GPUs) to dramatically speed up the computing applications.

## Prerequisites
For you to install CUDA, compile the CUDA programs, and run the CUDA programs on Ubuntu 22.04 LTS operating system, you need the following:
1. An installed NVIDIA GPU on your computer.

2. Installing GCC and Other Build Tools with the following command 
```sudo apt install build-essential```
GCC and the required packages are now being installed. It takes a while to complete. GCC and the required build tools for CUDA to work should be installed at this point.

To check whether you can access the GCC C and C++ compilers, run the following command:
```gcc --version```
```g++ --version```

3. Install Kernel Headers with the following command:
```sudo apt install linux-headers-$(uname -r)```

4. Installed NVIDIA GPU drivers on your Ubuntu operating system.

If you do not have Nvida Drivers in your system then follow this [Totorial](https://github.com/Mr-MeerMoazzam/Cuda-Setup-In-Ubunto-22.04/tree/main/Install%20Nvidia%20Drivers%20on%20Ubunto) to install NVIDIA GPU Drivers.

5. Updating the APT Package Repository Cache with the following command:
```sudo apt update```

## Install CUDA on Ubuntu
1. Check which version of CUDA is compatible with NVIDIA Driver Version you installed in your system from the [Official] (https://docs.nvidia.com/deploy/cuda-compatibility/index.html#minor-version-compatibility).
2. Go to the [NVIDIA Official](https://developer.nvidia.com/cuda-toolkit-archive) to download the required version of CUDA according to your hardware specification.

![image](https://github.com/Mr-MeerMoazzam/Cuda-Setup-In-Ubunto-22.04/assets/98279854/ce0e301f-7c7d-458e-ae79-270c29942c40)

As in my case CUDA 11.4.4 is copatible with my GPU Driver version. I clicked on CUDA Toolkit 11.4.4. and Select my target plateform.

![image](https://github.com/Mr-MeerMoazzam/Cuda-Setup-In-Ubunto-22.04/assets/98279854/c0be8b1b-3b21-4b95-acf4-ebcdb05b0540)

Now Here you will see a set of commands to install the required CUDA version.

![image](https://github.com/Mr-MeerMoazzam/Cuda-Setup-In-Ubunto-22.04/assets/98279854/efce24d4-82b1-47fb-b9d3-a7e5201944bc)


The last line is tricky and confusing for most people. Since it installs the most recent Cuda version, and shouldn’t be used if you don’t want the latest version of CUDA. Instead of executing 
```sudo apt-get install cuda``` 
Execute "sudo apt-get install cuda-X-X" As in my case.
```sudo apt-get install cuda-11-4``` 

CUDA and the required packages are now being downloaded and being installed. It takes a while to complete.

2. To check if CUDA is installed successfully on Ubuntu, run the following command:
```nvcc --version```

## Install CUDNN
To install cuDNN, you need to login to Nvidia website and download the tar.gz version using this official link.
