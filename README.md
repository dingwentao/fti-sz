What is FTI-SZ?
FTI-SZ is a lossy checkpointing library integrated FTI multi-level checkpointing library with SZ lossy compression library.
It can significantly improve the checkpointing performance.

What is FTI?
FTI stands for Fault Tolerance Interface and is a library that aims to give
computational scientists the means to perform fast and efficient multilevel
checkpointing in large scale supercomputers. FTI leverages local storage plus
data replication and erasure codes to provide several levels of reliability and
performance. FTI is application-level checkpointing and allows users to select
which datasets needs to be protected, in order to improve efficiency and avoid
wasting space, time and energy. In addition, it offers a direct data interface
so that users do not need to deal with files and/or directory names.  All
metadata is managed by FTI in a transparent fashion for the user. If desired,
users can dedicate one process per node to overlap fault tolerance workload and
scientific computation, so that post-checkpoint tasks are executed
asynchronously.

---

Download, compile and install FTI-SZ (as easy as 1,2,3)
=

 1) git clone git@github.com:dingwentao/fti-sz.git
 2) mkdir fti-sz/build && cd fti-sz/build
 3) cmake -DCMAKE_INSTALL_PREFIX:PATH=/install/here/fti .. && make all install

> **REMARK 1** (Intel and GCC)  
> For the case that both, **Intel and GCC**, compilers are installed, please configure using:  
> `cmake -C ../intel.cmake -DCMAKE_INSTALL_PREFIX:PATH=/install/here/fti-sz ..`

> **REMARK 2** (OpenSSL)  
> To use the built-in MD5 rather than OpenSSL, please configure using:  
> `cmake -DNO_OPENSSL=true -DCMAKE_INSTALL_PREFIX:PATH=/install/here/fti-sz ..`

> **REMARK 3** (GNU versions)  
> The usage of different GNU compiler versions for C and Fortran leads currently to an undefined behavior. Please make sure the compiler identification for C and Fortran is the same.

> **REMARK 4** (Cray System)  
> FTI-SZ works on Cray system with these modules  
> GNU environment:  
> `module load gcc/5.3.0 CMake/3.6.2 craype/2.5.8 cray-mpich/7.5.0 PrgEnv-gnu/6.0.3 `  
> `export CRAY_CPU_TARGET=x86-64`  
> `export CRAYPE_LINK_TYPE=dynamic`  
> Flag for CMake: `-CMAKE_SYSTEM_NAME=CrayLinuxEnvironment`  
>  
> Intel environment:  
> `module load intel/17.0.1.132 CMake/3.6.2 craype/2.5.8 cray-mpich/7.5.0 PrgEnv-intel/6.0.3`  
> `export CRAY_CPU_TARGET=x86-64`  
> `export CRAYPE_LINK_TYPE=dynamic`  
> Flag for CMake: `-CMAKE_SYSTEM_NAME=CrayLinuxEnvironment`  
>  
> The most important is CMake version: the newer the better.  

---

Configure and run a FTI-SZ example
=

The "build/examples" directory contains heat distribution simulations as simple
examples in both, C and Fortran. Usage instructions in file "examples/README".

---

