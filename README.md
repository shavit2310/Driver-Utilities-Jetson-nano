# Driver-Utilities-Jetson-nano
This is a presentation based on an ADAS project which elaberate some missing utilities for drivers:
Driver Utilities: Forward Collision , Lane departure, Traffic sign detection  &amp; Over speed 
STILL WORKING ON

## Table of Contents

    * [System Setup](#System-Setup)
    * [Walkthroughs](#Walkthroughs)
    * [API Reference](#API-Reference)
    * [Code Examples](#Code Examples) - Scope of functionalities 
    * [Pre-Trained Models (?)](#Pre-Trained-Models)
    * [Extra Resources](#Extra-Resources)
    * [Future improvments](#Future-improvments)
    
## System Setup
  ### Jetson Nano set-up
        Set-up the jetson nano from:  Getting Started with Jetson Nano Developer Kit, follow the explanations of how to flash SD
  ### System Requirements
        1. Check the project requirements, and verify the HW & SW are satisfied:
           Support python 3.6.9.
           Requirements:
              a. CMake >= 3.10     >> cmake --version
              b. Qt 5              >> qmake --version
              c. OpenCV >= 4.0.1   >> opencv: /usr/bin/opencv_version
              d. C++ 17 compiler   >> gcc -v --help 2> /dev/null | sed -n '/^ *-std=\([^<][^ ]\+\).*/ {s//\1/p}' 
                                                   >> in the list should be c++17. The gcc --version command or g++ does not reveal the version of C++ compiler
              e. protobuf 3.6.1>>> pip3 show protobuf
              f. CUDA 10.1 or 10.2 >> nvcc --version >>  cd /usr/local/ + nvcc --version Or cat /usr/local/cuda/version.txt
                  [nvidia-smi >> command does not supported on tagra architecture]
              g.TensorRT 5.1.5-1 (for CUDA cuda10.1) - TensorRT 6.0.1.8 (for CUDA 10.2)
                  [This project should work with TensorRT 5 and TensorRT 6. TensorRT 7 is not supported for now].
          2. If the requirements not met:
             a. For Qt & OpenCv follow ReadMe on https://github.com/vietanhdev/open-adas
             b. For Cmake installation, Follow:XXXXXXXXXXXX
             C. If C++ compiler is not as required , The project probably will not run. Should be tested.
             d. For protobuf do: 1. git clone https://github.com/protocolbuffers/protobuf -bv3.6.1
                                 2. cd protobuf
                                 3. autoreconf -if
                                 4. ./configure
                                 5. make
                                 6. make install
             e. For CUDA : YYYYYYYYY
             f. For TensorRT: a. For installation: ZZZZZZZZZZZ
                              b. One of 3 elements is a tar file, that provides more flexibility, such as installing multiple versions of TensorRT at the same time. 
                                 In the case of the Uploading version - it's

         3. Getting the Project - Build the Project from Source 
      
## Walkthrough
## API Reference
  Python
  Image Recognition 	imageNet 	
  Object Detection 	 	detectNet
  Segmentation 	 	    segNet

  These libraries are able to be used in external projects by linking to libjetson-inference and libjetson-utils.
  
## Code Examples

  Introductory code walkthroughs of using the library are covered during these steps of the Hello AI World tutorial:
  
## Pre-Trained Models

## Extra Resources

  In this area, links and resources for this project:

   
    
    
    

