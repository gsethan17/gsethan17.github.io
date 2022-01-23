# gsethan17.github.io

i will make my blog for my engineering activities referring the below blog.  
[Reference blog link](https://zeddios.tistory.com/1222)

It will have below contents.
1. Checking the Computer components  
    * CPU check on ubuntu  
    ```
    $ cat /proc/cpuinfo
    ```

    * GPU check on ubuntu  
    ```
    $ lspci | grep VGA
    
    # if you meet the comment as bellow, you need to update pci ids.  
    "65:00.0 VGA compatible controller: NVIDIA Corporation Device 2208 (rev a1)"
    
    # update pci ids for gpu  
    $ sudo update-pciids
    
    # In my case, I checked the output as below.
    "65:00.0 VGA compatible controller: NVIDIA Corporation GA102 [GeForce RTX 3080 Ti] (rev a1)"
    ```
    
    * Ubuntu version check
    ```
    $ lsb_release -d
    "Description:    Ubuntu 20.04.3 LTS"
    ```
   
2. CUDA & cuDNN setup
    * install nvidia-driver   
    ```
    # install nvidia-drivers-common
    $ sudo apt-get -y install ubuntu-drivers-common

    # check the recommended nvidia driver for the installed GPU model
    $ ubuntu-drivers devices


    # install nvidia-driver-470
    $ sudo apt install nvidia-driver-460

    # reboot the system
    $ sudo reboot now
    ```

    * install CUDA  
    please check the CUDA version for tensorflow through [Tensorflow supported GPU](https://www.tensorflow.org/install/gpu)  
    please check the install comands through [CUDA Toolkit Archive](https://developer.nvidia.com/cuda-toolkit-archive)  
    ```
    # In my case, install CUDA version 11.2.2 by below commands
    $ wget https://developer.download.nvidia.com/compute/cuda/11.2.2/local_installers/cuda_11.2.2_460.32.03_linux.run
    $ sudo sh cuda_11.2.2_460.32.03_linux.run
    # when you install the CUDA, you can install nvidia-driver with CUDA

    # After installation, please add the path command in .bashrc
    $ vim ~/.bashrc
    $ # NVIDIA CUDA toolkit
    $ export PAHT=/usr/local/cuda-11.2/bin:$PATH
    $ export LD_LIBRARY_PATH=/usr/local/cdua-11.2/lib64
    $ :wq
    $ source ~/.bashrc
    ```



    ```

    * install cuDNN
    pleas check the cuDNN version for tensorflow through [Tensorflow supported GPU](https://www.tensorflow.org/install/gpu)  

    
    # In my case, install cuDNN version SDK 8.1.0 by below commands

    ```

    
