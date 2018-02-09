Download, compile and install lossy checkpointing (as easy as 1,2,3)

1) git clone https://github.com/dingwentao/lossy-checkpoint.git
2) mkdir lossy-checkpoint/build && cd lossy-checkpoint/build
3) cmake -DCMAKE_INSTALL_PREFIX:PATH=[installation path] .. && make all install

Intel and GCC
For the case that both Intel and GCC compilers are installed, please configure using:  
`cmake -C ../intel.cmake -DCMAKE_INSTALL_PREFIX:PATH=[installation path] ..`

OpenSSL
To use the built-in MD5 rather than OpenSSL, please configure using:  
`cmake -DNO_OPENSSL=true -DCMAKE_INSTALL_PREFIX:PATH=/install/here/fti-sz ..`

Cray System
Lossy checkpointing library  works on Cray system with these modules  
GNU environment:  
`module load gcc/5.3.0 CMake/3.6.2 craype/2.5.8 cray-mpich/7.5.0 PrgEnv-gnu/6.0.3 `  
`export CRAY_CPU_TARGET=x86-64`  
`export CRAYPE_LINK_TYPE=dynamic`  
Flag for CMake: `-CMAKE_SYSTEM_NAME=CrayLinuxEnvironment`  
  
Intel environment:  
`module load intel/17.0.1.132 CMake/3.6.2 craype/2.5.8 cray-mpich/7.5.0 PrgEnv-intel/6.0.3`  
`export CRAY_CPU_TARGET=x86-64`  
`export CRAYPE_LINK_TYPE=dynamic`  
Flag for CMake: `-CMAKE_SYSTEM_NAME=CrayLinuxEnvironment`  

The most important is CMake version: the newer the better.  

Configure and run example

The "build/examples" directory contains heat distribution simulations as simple
examples in both, C and Fortran. Usage instructions in file "examples/README".
