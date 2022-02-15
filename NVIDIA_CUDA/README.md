# Install NVIDIA CUDA Toolkit on CentOS 7 Linux step by step instructions

Download the NVIDIA CUDA repository package from this [link](https://developer.download.nvidia.com/compute/cuda/repos/rhel7/x86_64/)

You can use [wget](https://www.gnu.org/software/wget/) to download the CUDA package

```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/rhel7/x86_64/cuda-repo-rhel7-10.0.130-1.x86_64.rpm
```

If you want to install CUDA on a custom directory (not in /usr/local) then you may follow the steps for a non-interactive installation.

```bash
./runfile.run --silent --toolkit --toolkitpath=/my/new/toolkit --samples --samplespath=/my/new/samples
```

To install the RPM packages in custom locations using rpm's --relocate parameter

```bash
rpm --install --relocate /usr/local/cuda-6.5=/my/new/toolkit rpmpackage.rpm
```

 To install the Deb packages in custom locations using dpkg's -- instdir parameter
 
 ```bash
 dpkg --instdir=/my/new/toolkit --install debpackage.deb
 ```
 
 Install CUDA
 
 ```bash
 yum install cuda
 ```
 Export the path to Nvidia CUDA binary executables. Open the ```vi ~/.bashrc``` and write.
 
 ```bash
export PATH=/my/new/toolkit/bin:/my/new/toolkit/nsight-compute-2021.3.0${PATH:+:${PATH}}
export LD_LIBRARY_PATH=//my/new/toolkit/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
 ```
 
 Update the ```~/.bashrc``` file
 
 ```bash
 source ~/.bashrc
 ```
 
 Check the correct CUDA version
 
 ```bash
nvcc --version
nvidia-smi
 ```
