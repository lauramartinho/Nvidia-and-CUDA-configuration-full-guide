## CUDA Toolkit configuration for UBUNTU 

The **CUDA** (Compute Unified Device Architecture) is a parallel computing platform and programming model created by Nvidia, which allows developers to use GPUs for general-purpose computing tasks. Together with the Nvidia drivers, the CUDA Toolkit provides the tools needed to develop and optimize applications that take advantage of the power of Nvidia graphics cards.

* To see the main page of the complete tutorial access [Nvidia Drivers configuration and verification for UBUNTU](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide).
* To see the installation of the NVIDIA Drivers go to [the NVIDIA Drivers Installation Guide](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/blob/main/nvidia-drivers.md).
* To check and test the nvidia and cuda installations on your computer, go to [NVIDIA and CUDA testing guide](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/blob/main/testing-cuda.md).


>❗ Make sure that you had already [installed the NVIDIA Drivers](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/nvidia-drivers.md) before following the CUDA toolkit configuration steps. 

## 1) Checking NVIDIA Driver 
Check the NVIDIA Driver installed in your system with the NVIDIA System Management Interface, as known as `nvidia-smi`. 
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

## 2) Installing GCC Compiler
The **gcc compiler** will be used to install the CUDA Toolkit. Check if the gcc has been installed next.
~~~
sudo apt install gcc
~~~
~~~
gcc -v
~~~
![Captura de tela de 2024-11-28 15-54-37](https://github.com/user-attachments/assets/0fb27e8f-b6be-40e9-8981-2b3e82ac9b2c)

## 3) Installing CUDA TOOLKIT
Now you got to access https://developer.nvidia.com/cuda-downloads to get the right package to your system, followed by steps to install it correctly. For Ubuntu, I recommend the **deb(network)** option. Follow and run each of the instalation instructions in your system.

![Captura de tela de 2024-11-28 15-58-40](https://github.com/user-attachments/assets/c06c5400-dd68-4651-bc7d-e9992df825e9)

If any errors occur during the installation, try `sudo apt --fix-broken install`. 
Now that the installation is done, reboot your system.
~~~
sudo reboot now
~~~

## 4) Add CUDA path to the environment variables
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

## 5) Check installation 

Now is time to check your installation with `nvcc -v` or `nvcc --version`:
~~~
nvcc --version
~~~
![Captura de tela de 2024-11-29 09-24-50](https://github.com/user-attachments/assets/68adb96b-4235-404f-8183-a4bc9adff978)

## 6) Verifying and testing the drivers
After installing the NVIDIA drivers and the CUDA Toolkit, you can run some tests to check that they are working correctly. Check the steps to confirm installation and operation at https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/testing-cuda.md
