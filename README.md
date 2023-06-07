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

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/eb83d9f2-9fdf-47d7-9b38-4eb28863f377)

As in my case CUDA 12.1 is copatible with my GPU Driver version. I clicked on CUDA Toolkit 12.1.0. and Select my target plateform.

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/cfed0da9-6053-4d84-a60b-31a92406f150)

Now Here you will see a set of commands to install the required CUDA version.

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/247ae292-e98f-48d2-a8f5-efacb3a9b466)

The last line is tricky and confusing for most people. Since it installs the most recent Cuda version, and shouldn’t be used if you don’t want the latest version of CUDA. Instead of executing 
```sudo apt-get install cuda``` 
Execute "sudo apt-get install cuda-X-X" As in my case.
```sudo apt-get install cuda-12-1``` 

CUDA and the required packages are now being downloaded and being installed. It takes a while to complete.

2. If you do nvidia-smi or nvcc — version now, they would not work because they are yet to be added to bashrc. Update bashrc now.  
Add the below lines to your bashrc.
```export PATH="/usr/local/cuda-12.1/bin:$PATH"
export LD_LIBRARY_PATH="/usr/local/cuda-12.1/lib64:$LD_LIBRARY_PATH"
```
Instead of "cuda-12.1", replace with your specific veresion of cuda.

After which do,

```source .bashrc```

3. To check if CUDA is installed successfully on Ubuntu, run the following command:
```nvcc --version```

## Install CUDNN
To install cuDNN, you need to login to Nvidia website and download the tar.gz version using this official link.
