## Verify NVIDIA and CUDA installation integrity 
CUDA Samples are code examples provided by NVIDIA to demonstrate how to use the CUDA Toolkit and exploit the features of NVIDIA GPUs for parallel computing. They are extremely useful for learning, testing, and developing applications that take advantage of the parallel processing offered by GPUs.

* To see the installation of the NVIDIA Drivers go to [the NVIDIA Drivers Installation Guide](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/blob/main/nvidia-drivers.md).
* To see the installation of the cuda toolkit go to [the CUDA Toolkit Installation Guide](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/blob/main/cuda-toolkit.md).
* To check and test the nvidia and cuda installations on your computer, go to [NVIDIA and CUDA testing guide](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/blob/main/testing-cuda.md).

>❗ Make sure that you had already [installed the NVIDIA Drivers](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/nvidia-drivers.md) and [CUDA Toolkit](https://github.com/lauramartinho/Nvidia-and-CUDA-configuration-full-guide/cuda-toolkit.md) before following the sample tests steps. 

## 1) Getting CUDA samples
Visit the [Cuda Samples repository](https://github.com/nvidia/cuda-samples) to git clone the latest version
~~~
git clone https://github.com/NVIDIA/cuda-samples.git
~~~

## 2) Building the directory
CUDA samples on Linux are compiled with Makefiles. Navigate to the directory of the sample to compile
~~~ 
cd /cuda-samples/Samples/1_Utilities/deviceQuery
make
~~~

Linux samples are built using makefiles, access the sample directory and run make:
~~~
cd <sample_dir>
make
~~~

## 3) Running the Examples
After compilation, run the generated binary. In the case of deviceQuery:
~~~
./deviceQuery
~~~
Detailed information about your GPU will be displayed:

![Captura de tela de 2024-11-29 15-17-52](https://github.com/user-attachments/assets/060f973f-eb1f-4ea8-a837-adc320c092f0)
