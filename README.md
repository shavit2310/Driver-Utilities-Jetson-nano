# Driver-Utilities-Jetson-nano
This is a presentation based on an ADAS project which elaborate some missing utilities for drivers:
Driver Utilities: Forward Collision , Lane departure, Traffic sign detection  &amp; Over speed 
STILL WORKING ON       

## Table of Contents
* [General info](#general-info)
* [Setup](#setup)
* [WalkThrough](#WalkThrough)
* [API REFERENCE](#API-REFERENCE)
* [Code example](#Code-example)
* [Pre-trained Models-?](#Pre-trained-Models-?)
* [Extra Resources](#Extra-Resources)
* [Future improvements](#Future-improvements)
    
## General info
This project is simple Lorem ipsum dolor generator.
## SetUp
This project is simple Lorem ipsum dolor generator.
	
  ### Jetson Nano set-up   

      Set-up the jetson nano from the: ![explanations here](https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit)       
  
  ### System requirements   

      A. Verify requirements:     

         >>Verify python =>3.6.9.             
         >>Verify  Ubuntu 18.04.          
         >>Verify Jetson Nano 4GB. 64GB-SD.          
       
        | Application          | Verify By                                                                                         |
        | -------------------- | ------------------------------------------------------------------------------------------------- |	
        | Cmake >= 3.10        | cmake --version                                                                                   |
        | Qt 5                 | qmake --version                                                                                   |    
        | OpenCV >= 4.0.1      | opencv: /usr/bin/opencv_version                                                                   |
        | C++ 17 compiler      | gcc -v --help 2> /dev/null | sed -n '/^ *-std=\([^<][^ ]\+\).*/ {s//\1/p}'                        |                                        
        |                                                  >> Find c++17 in the list.                                              | 
        | protobuf 3.6.1       | pip3 show protobuf                                                                                |
        | CUDA 10.1 or 10.2    | nvcc --version >>  cd /usr/local/ + nvcc --version Or cat /usr/local/cuda/version.txt             |
        |                      |                           >> [nvidia-smi >> command does not support tagra, its a work around]    |  
	|                      | cudnn version  >>  dpkg -l | grep cudnn							   |
        | TensorRT 5.1.5       | dpkg -l | grep TensorRT  >> [TensorRT 7 is not supported for now].                                |
        |   OR 6.0.1.8         |                                                                                                   | 


      B. You can use this Installation list where gaps are found out:      
         1. ![For openCV](#https://qengineering.eu/install-opencv-4.5-on-jetson-nano.html)\
         2. For QT installation, 

	      $ sudo apt-get install build-essential
	      $ sudo apt-get install qt5-default qtcreator qt5-doc qt5-doc-html qtbase5-doc-html qtbase5-examples -y
	      $ sudo /sbin/ldconfig -v
	      
         3. For Cmake installation, 

	      $ sudo apt-get install software-properties-common
	      $ sudo add-apt-repository ppa:george-edison55/cmake-3.x
	      $ sudo apt-get update.         When cmake is not yet installed:
	      $ sudo apt-get install cmake.  When cmake is already installed:
	      $ sudo apt-get upgrade
	      $ sudo apt-get install build-essential
	      $ wget http://www.cmake.org/files/v3.2/cmake-3.20.0.tar.gz
	      $ sudo tar xf cmake-3.20.0.tar.gz
	      $ cd cmake-3.20.0
	      $ sudo ./configure && make 
	      $ sudo make install

         3. If C++ compiler is not as required , The project probably will not run. Should be tested.  
         4. For protobuf do: 

              $ git clone https://github.com/protocolbuffers/protobuf -bv3.6.1 
              $ cd protobuf
              $ autoreconf -if  
              $ ./configure
              $ make
              $ make install      
	      $ pip3 show protobuf 
	      if version not 3.6.1:
	      $ pip3 install --upgrade protobuf==3.6.1
            
         5. For CUDA :  ![Version CUDA10.1](#https://medium.com/@exesse/cuda-10-1-installation-on-ubuntu-18-04-lts-d04f89287130), 
                        Make necessary adaptations if CUDA 10.2 is required.     
         6. For TensorRT:Provided flexibility, such as installing multiple versions of TensorRT at the same time.    
                         Since in this project we needed to downgrade the version, from the version granted inrhe JetPeck4.5.1, 
			 ![we install another TensorRT version:](#https://docs.donkeycar.com/guide/robot_sbc/tensorrt_jetson_nano/)
    
   ### Build the Project from Source  

         Python Development Packages
         1. For Python 3, install these packages before proceeding:

              $ sudo apt-get install libpython3-dev python3-numpy

         2. Clone source 
              $ cd ~   
              $ mkdir Works
              $ cd Works
              $ git clone https://github.com/vietanhdev/open-adas
	       
	 3. Update GPU ARCHS
              Modify CMakeLists.txt : 		GPU_ARCHS = 53  
	      To suit your GPU, of the Jetson Nano, https://developer.nvidia.com/cuda-gpus
	      To support nvcc command:  	SET(CMAKE_CUDA_COMPILER /usr/local/cuda/bin/nvcc)
	       	       
         4. Build 
              $ mkdir build
              $ cd build
              $ cmake ../
	      
	 5. ![Downloads models & data sample](#https://drive.google.com/drive/folders/1-DDchZQNOWpppNX8udyKj0OViDhYD38O)
            and extract it to open-adas/models and open-adas/data, respectively.
	      
	 6. Setup virtual CAN (run only once)
 	 
	      $ cd Works/open-adas/build/bin
	      $ sudo bash setup_vcan.sh
	       
	 7. Run 
              $ ./OpenADAS
	       
     The project will be built to XXXXX/build/aarch64, with the following directory structure:

      |-build
         \aarch64
            \bin             where the sample binaries are built to
               \networks     where the network models are stored
               \images       where the test images are stored
            \include         where the headers reside
            \lib             where the libraries are build to

      In the build tree, you can find the binaries residing in build/aarch64/bin/, headers in build/aarch64/include/, and libraries in build/aarch64/lib/. 
      These also get installed under /usr/local/ during the sudo make install step.

      The Python bindings for the PROJECT and jetson.utils modules also get installed during the sudo make install step under /usr/lib/python*/dist-packages/. 
      If you update the 
      code, remember to run it again.    
      
      FOR B&R 
      II. Build and Run

 ## WalkThrough
This project is simple Lorem ipsum dolor generator.
		    
   Digging Into the Code

## API REFERENCE
Python
  Image Recognition 	imageNet 	
  Object Detection 	 detectNet
  Segmentation 	 	 segNet

  These libraries are able to be used in external projects by linking to ZZZZZ and XXXXX.

## Code example
  Introductory code walkthroughs of using the library are covered during these steps of the Hello AI World tutorial:
  
## Pre-trained Models-?
This project is simple Lorem ipsum dolor generator.

## Extra Resources
This project is simple Lorem ipsum dolor generator.

## Future improvements
This project is simple Lorem ipsum dolor generator.
	

  
    
    

