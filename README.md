## Nvidia Drivers and CUDA Toolkit configuration and verification for UBUNTU full guide

This guide aims to provide detailed steps for setting up Nvidia drivers and the CUDA toolkit on Ubuntu, allowing you to take full advantage of the parallel processing capabilities of Nvidia GPUs.

**Nvidia** is a leading company in the GPU market, specializing in graphics technology, artificial intelligence, machine learning and scientific computing, with high performance and parallel processing capabilities. The **CUDA** (Compute Unified Device Architecture) is a parallel computing platform and programming model created by Nvidia, which allows developers to use GPUs for general-purpose computing tasks. Together with the Nvidia drivers, the CUDA Toolkit provides the tools needed to develop and optimize applications that take advantage of the power of Nvidia graphics cards.


- By using CUDA, you can transfer part of the workload from the processor (CPU) to the GPU, taking advantage of the parallel processing capability of Nvidia graphics cards. This results in much faster performance for tasks such as neural network training, 3D rendering and simulations. The CUDA Toolkit offers a series of libraries and tools that facilitate the development of AI applications, including deep neural networks, supervised and unsupervised learning, and analysis of large volumes of data. It is essential for any project involving deep learning and large volumes of data. To get the most out of Nvidia GPUs, you need to configure the drivers and the CUDA Toolkit correctly. This ensures that you are using the full capacity of your graphics card efficiently and without errors.


## Upgrading Ubuntu
To make sure you have all the latest software, upgrade the system.
~~~
sudo apt update
sudo apt upgrade 
~~~

## 1) Installing NVIDIA Drivers
When installing the `ubuntu-drivers-common` you are going to be able to get a list with all drivers available for your system, plus a recommended one.
~~~
sudo apt install ubuntu-drivers-common
sudo ubuntu-drivers devices
~~~

![Captura de tela de 2024-11-28 15-27-23](https://github.com/user-attachments/assets/85850aa8-7f60-4612-89d7-c6ad3ff06cb7)

The `ubuntu-drivers` command lists the NVIDIA GPU installed and also recommends the driver 565. Download the recommended version for your system:
~~~
sudo apt install nvidia-driver-<recommended>
~~~

After installing the NVIDIA Drivers you must reboot the system to make sure everything has processed correcty.
~~~
sudo reboot now
~~~

Now is time to check your installation with the NVIDIA System Management Interface, as known as `nvidia-smi`. 
~~~
nvidia-smi
~~~
![Captura de tela de 2024-11-28 15-42-12](https://github.com/user-attachments/assets/86643d73-2aef-4afb-92b4-818f18f49035)

At the top of the table, you can see the installed driver version and CUDA driver API compatibility.
~~~
+-----------------------------------------------------------------------+
|NVIDIA-SMI 560.35.03    Driver Version: 560.35.03    CUDA Version: 12.6|
|-------------------------------------------+---------------------------+
~~~
_In my case, I already have installed the NVIDIA 560 driver wich was recommended before, and that works good for me by now, although I got 565 recommended earlier._

## 2) Installing CUDA TOOLKIT
The **gcc compiler** will be used to install the CUDA Toolkit. Check if the gcc has been installed next.
~~~
sudo apt install gcc
~~~
~~~
gcc -v
~~~
![Captura de tela de 2024-11-28 15-54-37](https://github.com/user-attachments/assets/0fb27e8f-b6be-40e9-8981-2b3e82ac9b2c)

Now you got to access https://developer.nvidia.com/cuda-downloads to get the right package to your system, followed by steps to install it correctly. For Ubuntu, I recommend the **deb(network)** option. Follow and run each of the instalation instructions in your system.

![Captura de tela de 2024-11-28 15-58-40](https://github.com/user-attachments/assets/c06c5400-dd68-4651-bc7d-e9992df825e9)

If any errors occur during the installation, try `sudo apt --fix-broken install`. 
Now that the installation is done, reboot your system.
~~~
sudo reboot now
~~~

Verify the cuda folders you downloaded:
~~~
cd /usr/local/
~~~
![Captura de tela de 2024-11-28 16-24-18](https://github.com/user-attachments/assets/292097ed-7f6a-4f99-a235-954fa4c9a2ef)

As you can see, there is a cuda-12.6 folder, corresponding to the toolkit downloaded. 

To complete the setup, you need to update the envinronment variables accessing the `.bashrc file` as recommended by [NVIDIA Documentation](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#post-installation-actions).
~~~
nano ~/.bashrc
~~~

Add the CUDA path in the end of the file.
~~~
export PATH=/usr/local/cuda-<version>/bin${PATH:+:${PATH}}
~~~
Save by `ctr+o` + `enter` and exit the file by `ctr+x`. You have to reload the file by the command:
~~~
. ~/.bashrc
~~~

Now is time to check your installation with `nvcc -v` or `nvcc --version`:
~~~
nvcc --version
~~~
![Captura de tela de 2024-11-29 09-24-50](https://github.com/user-attachments/assets/68adb96b-4235-404f-8183-a4bc9adff978)

## 3) Verifying and testing the drivers


⚠️ :warning:	TO BE CONTINUED...





