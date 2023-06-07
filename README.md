# Cuda-CUDNN-Setup-In-Ubunto-20.04
In this repo, I will show you how to install CUDA, CUDNN on Ubuntu 20.04 LTS. I will also show you how to write, compile, and run your very first CUDA program on Ubuntu 20.04 LTS as well to ensure the succussfully installation.
## Cuda
The full form of CUDA is Compute Unified Device Architecture. CUDA is a parallel computing platform and programming model developed by NVIDIA. It is used to run the programs on NVIDIA Graphics Processing Units (GPUs) to dramatically speed up the computing applications.

## Prerequisites
For you to install CUDA, compile the CUDA programs, and run the CUDA programs on Ubuntu 20.04 LTS operating system, you need the following:
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
1. Check which version of CUDA is compatible with NVIDIA Driver Version you installed in your system from the [NVIDIA Official](https://docs.nvidia.com/deploy/cuda-compatibility/index.html#minor-version-compatibility) or you can see the compatible version of cuda with your installed Driver version by running ```nvidia-smi``` on your terminal.
2. Go to the [NVIDIA Official](https://developer.nvidia.com/cuda-toolkit-archive) to download the required version of CUDA according to your hardware specification.

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/eb83d9f2-9fdf-47d7-9b38-4eb28863f377)

As in my case CUDA 11.4 is compatible with my GPU Driver version. I clicked on CUDA Toolkit 11.4.4. and Select my target plateform.

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/c722fcc3-8309-4491-bf22-50b43358fc00)


Now, you will see a set of commands to runfile locally.

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/c0a89be1-c811-472c-8b46-16978f75ff9a)


2. If you do nvidia-smi or nvcc — version now, they would not work because they are yet to be added to bashrc. Update bashrc now.  
Add the below lines to your bashrc.

```export PATH="/usr/local/cuda-11.4/bin:$PATH"```

```export LD_LIBRARY_PATH="/usr/local/cuda-11.4/lib64:$LD_LIBRARY_PATH"```

Instead of "cuda-11.4", replace with your specific veresion of cuda.

After this run the following command to activate the environment variable,

```source .bashrc```

3. To check if CUDA is installed successfully on Ubuntu, run the following command:
```nvcc --version``` and ```nvidia-smi```

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/5ac919f0-70e2-4e32-bc20-155d562f2b79)

4. If you found that after installing the CUDA version, the driver version is changed then uninstall the cuda version and driver, again install the required driver and run the command below to install CUDA 11.4.3:

```
wget https://developer.download.nvidia.com/compute/cuda/11.4.3/local_installers/cuda_11.4.3_470.82.01_linux.run
```
### Testing the installation of CUDA 
1. Create a new virtual environment and activate it as well (Recommended):
```conda create -n new_env python=3.8```
```conda activate new_env```
2. Install the required libraries by running the command
```conda install pytorch torchvision cudatoolkit=10.1 -c pytorch```
```conda install tensorflow-gpu```
3. It will install PyTorch and TensorFlow. To check if they are working: Open python terminal now and import TensorFlow and torch inside it. Now, do:
``` torch.cuda.is_available()```
If it returns True, the torch is able to use GPU. Check for TensorFlow now. If the below command shows GPU name then Tensorflow is working with GPU as well.
```print (tf.test.gpu_device_name())```
Now, nvidia-smi, nvcc — version both would work, and in fact, torch and Tensorlfow are able to use GPUs as well. 

## Install CUDNN
1. To install cuDNN, you need to login to Nvidia website and download the tar.gz version of CUDNN that is compatible with your CUDA version using this [official link](https://developer.nvidia.com/rdp/cudnn-archive).

2. Once downloaded extract the downloaded file and copy the necessary contents to the cuda directory. Navigate the download file directory and run the following commands.

```sudo dpkg -i cudnn-local-repo-ubuntu2004-8.9.1.23_1.0-1_amd64.deb```
``` sudo cp /var/cudnn-local-repo-ubuntu2004-8.9.1.23/cudnn-local-A9C84908-keyring.gpg /usr/share/keyrings/```
```sudo apt update```

3. Now Run ```sudo apt list libcudnn8 -a``` command to check available versions of libcudnn8 for CUDA. From CUDA 11.6 and onwwards, the cuDNN version does not need to be.

![image](https://github.com/Mr-MeerMoazzam/Set-Up-CUDA-cuDNN-on-Ubuntu-20.04/assets/98279854/21b0db47-b805-47a4-878b-fa00dda4b6bf)

4. In accordance with installed CUDA version. Now replace the x.x.x and X.Y with latest version numbers obtained in upcoming commands. 
5. Install the runtime library By running the following command.
``` sudo apt install libcudnn8=8.x.x.x-1+cudaX.Y```
As in my case
``` sudo apt install libcudnn8=8.9.2.26-1+cuda12.1```
6. Install the developer library By running the following command.
``` sudo apt install libcudnn8-dev=8.x.x.x-1+cudaX.Y```
As in my case 
``` sudo apt install libcudnn8-dev=8.9.2.26-1+cuda12.1```
7. Install code samples and the cuDNN library documentation By running the following command.
``` sudo apt install libcudnn8-samples=8.x.x.x-1+cudaX.Y```
As in my case 
``` sudo apt install libcudnn8-samples=8.9.2.26-1+cuda12.1```
8. Now reboot your system by running the following command
```sudo reboot```



### Testing the installation of cuDNN

1. Install library ```sudo apt-get install libfreeimage3 libfreeimage-dev```
2. Copy he cuDNN samples to a writable path.
```cp -r /usr/src/cudnn_samples_v8/ $HOME```
3. Go to the writable path.
```cd  $HOME/cudnn_samples_v8/mnistCUDNN```
4. Compile the mnistCUDNN sample.
``` make clean && make```
5. Run the mnistCUDNN sample.
```./mnistCUDNN```
6. If cuDNN is properly installed and running on your Linux system, you will see a message similar to the following:
```Test passed!```
Note. If Test Passed is not displayed then maybe a missing package needs to be installed. Please install the packages mentioned in terminal output and perfom step 4 again. You can ignore any warnings appearing after this procedure and this validates the cuDNN installation.
