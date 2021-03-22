# Driver-Utilities-Jetson-nano
This is a presentation based on an ADAS project which elaberate some missing utilities for drivers:
Driver Utilities: Forward Collision , Lane departure, Traffic sign detection  &amp; Over speed 
STILL WORKING ON

## Table of Contents

    ### System Setup  
    ### Walkthroughs  
    ### PI Reference  
    ### Code Example - Scope of functionalities       
    ### Pre-Trained Models (?)  
    ### Extra Resources    
    ### Future improvements  
    
    
## System Setup #  
  ### Jetson Nano set-up #  
      Set-up the jetson nano from: ![follow explanations Here](https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit)       \
  ### System Requirements #       
      A. Verify requirements:  
         Install python 3.6.9.  
   > > Ubuntu 18.04.  
   > > Nvidia Jetson Nano 4GB , SD 64 GB.  
         
         a. CMake >= 3.10   <t>  > > cmake --version    \
         b. Qt 5           <t>   > > qmake --version     \
         c. OpenCV >= 4.0.1 <t>  > > opencv: /usr/bin/opencv_version    \
         d. C++ 17 compiler      > > gcc -v --help 2> /dev/null | sed -n '/^ *-std=\([^<][^ ]\+\).*/ {s//\1/p}'  
                                                   >> Find c++17 in the list.                
         e. protobuf 3.6.1       > > pip3 show protobuf    
         f. CUDA 10.1 or 10.2    > > nvcc --version >>  cd /usr/local/ + nvcc --version Or cat /usr/local/cuda/version.txt   
                                                    >> [nvidia-smi >> command does not support tagra architecture]      
         g. TensorRT 5.1.5-TensorRT 6.0.1.8 (compactable to CUDA version) > >    
                                                   >> [TensorRT 7 is not supported for now].  

      B. You can use this Installation list where gaps are found out:      
         a. [For Qt & OpenCv follow] (https://github.com/vietanhdev/open-adas) [OR this] (https://qengineering.eu/install-opencv-4.5-on-jetson-nano.html
)
         b. For Cmake installation, Follow:XXXXXXXXXXXX  
         C. If C++ compiler is not as required , The project probably will not run. Should be tested.  
         d. For protobuf do:   
                             '''
                             git clone https://github.com/protocolbuffers/protobuf -bv3.6.1  
                             cd protobuf  
                             autoreconf -if  
                             ./configure  
                             make  
                             make install 
                             '''
         e. For CUDA : The requirements are for CUDA 10.1 or CUDA 10.2.. [FOR CUDA10.1](#https://medium.com/@exesse/cuda-10-1-installation-on-ubuntu-18-04-lts-d04f89287130)                           use the necessary adaptations for the CUDA 102. version.  
         f. For TensorRT: One of 3 elements is a tar file, that provides more flexibility, such as installing multiple versions of TensorRT at the same time.  
                              Since in this project we needed to downgrade the version, we took this approach and kept 2 versions of TensorRT, due to dependencies complex.  
      C. Build the Project from Source  


      
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

   
    
    
    

