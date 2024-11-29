## Nvidia Drivers configuration and verification for UBUNTU 

**Nvidia** is a leading company in the GPU market, specializing in graphics technology, artificial intelligence, machine learning and scientific computing, with high performance and parallel processing capabilities. 

* To see the main page of the complete tutorial access [Nvidia Drivers configuration and verification for UBUNTU](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide).
* To see the installation of the cuda toolkit go to [the CUDA Toolkit Installation Guide](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/blob/main/cuda-toolkit.md).
* To check and test the nvidia and cuda installations on your computer, go to [NVIDIA and CUDA testing guide](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/blob/main/testing-cuda.md).

## 1) Upgrading Ubuntu
To make sure you have all the latest software, upgrade the system.
~~~
sudo apt update
sudo apt upgrade 
~~~

## 2) Installing NVIDIA Drivers
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

## 3) Check Installation
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

## 4) Next step is setting up the CUDA toolkit to be able to use the NVIDIA drivers. 
Check at https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/cuda-toolkit.md
