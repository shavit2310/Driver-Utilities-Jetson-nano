# Driver-Utilities-Jetson-nano
This is a presentation based on an ADAS project which elaberate some missing utilities for drivers:
Driver Utilities: Forward Collision , Lane departure, Traffic sign detection  &amp; Over speed 
STILL WORKING ON

## Table of Contents
    * [General info](#general-info)
    ### System Setup  
    ### Walkthroughs  
    ### PI Reference  
    ### Code Example - Scope of functionalities       
    ### Pre-Trained Models (?)  
    ### Extra Resources    
    ### Future improvements  
    
## General info    
## System Setup #  
  ### Jetson Nano set-up #  
      Set-up the jetson nano from: ![follow explanations Here](https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit)       \
  ### System Requirements #       
      A. Verify requirements:  
         Verify python =>3.6.9.  
         Verify Jetson Nan0 4GB. 64GB-SD.
         Verify Ubunru 18.04  

       
        | Application          | Verify By                                                                                                                                 |
        | ---                  | ---                                                                                                                                       |
        | CMake >= 3.10        | cmake --version`                                                                                                                          |
        | Qt 5                 | qmake --version                                                                                                                           | 
        | OpenCV >= 4.0.1      | opencv: /usr/bin/opencv_version`                                                                                                          |
        | C++ 17 compiler      |  gcc -v --help 2> /dev/null | sed -n '/^ *-std=\([^<][^ ]\+\).*/ {s//\1/p}'                                                               |                                        
        |                                               >> Find c++17 in the list.                                                                                         | 
        | protobuf 3.6.1       | pip3 show protobuf                                                                                                                        |
        | CUDA 10.1 or 10.2    | nvcc --version >>  cd /usr/local/ + nvcc --version Or cat /usr/local/cuda/version.txt                                                     |
                                                        >> [nvidia-smi >> command does not support tagra]                                                                  |  
        | TensorRT 5.1.5       | YYYTTTTTTTTTT  >> [TensorRT 7 is not supported for now].                                                                                  |
        |   OR 6.0.1.8         |                                                                                                                                           | 

      B. You can use this Installation list where gaps are found out:      
         a. ![For Qt & OpenCv follow] (#https://github.com/vietanhdev/open-adas) ![OR](#https://qengineering.eu/install-opencv-4.5-on-jetson-nano.html)  
         b. For Cmake installation, Follow:XXXXXXXXXXXX  
         c. If C++ compiler is not as required , The project probably will not run. Should be tested.  
         d. For protobuf do: 
            '''
            git clone https://github.com/protocolbuffers/protobuf -bv3.6.1  
            cd protobuf  
            autoreconf -if  
            ./configure  
            make  
            
            make install 
            '''  
         e. For CUDA :  [FOR CUDA10.1](#https://medium.com/@exesse/cuda-10-1-installation-on-ubuntu-18-04-lts-d04f89287130), use the necessary adaptations for CUDA 10.2.  
         f. For TensorRT:Provided flexibility, such as installing multiple versions of TensorRT at the same time.    
                         Since in this project we needed to downgrade the version, we took this approach and kept 2 versions of TensorRT. 
    
    C. Build the Project from Source  
      Python Development Packages
      By default, Ubuntu comes with the libpython-dev and python-numpy packages pre-installed. These development packages are required for the bindings to build using the 
      Python C API. So, if you want the project to create bindings for Python 3.6, install these packages before proceeding:

         $ sudo apt-get install libpython3-dev python3-numpy

      Configuring with CMake
      Next, create a build directory within the project and run cmake to configure the build. When cmake is run, a script is launched (CMakePreBuild.sh) that will install 
      any required dependencies and download DNN models for you.
      
      $ cd AAAAAAA   
      $ mkdir build
      $ cd build
      $ cmake ../

    note: this command will launch the CMakePreBuild.sh script which asks for sudo privileges while installing some prerequisite packages on the Jetson. 
    The script also downloads pre-trained networks from web services.
   Compiling the Project

   Make sure you are still in the ZZZZZZ/build directory, created above.

   Then run make followed by sudo make install to build the libraries, Python extension bindings, and code samples:

   $ cd DDDDDDDDD/build          # omit if working directory is already build/ from above
   $ make
   $ sudo make install
   $ sudo ldconfig

   The project will be built to jetson-inference/build/aarch64, with the following directory structure:

   |-build
      \aarch64
         \bin             where the sample binaries are built to
            \networks     where the network models are stored
            \images       where the test images are stored
         \include         where the headers reside
         \lib             where the libraries are build to

   In the build tree, you can find the binaries residing in build/aarch64/bin/, headers in build/aarch64/include/, and libraries in build/aarch64/lib/. 
   These also get installed under /usr/local/ during the sudo make install step.

   The Python bindings for the PRGECT and jetson.utils modules also get installed during the sudo make install step under /usr/lib/python*/dist-packages/. If you update the 
   code, remember to run it again.
   


      
## Walkthrough
Digging Into the Code
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

   
    
    
    

