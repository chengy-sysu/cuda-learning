## 环境配置

## docker

docker run -itd -v [要映射到容器内的A100路径]:[容器内的路径] --privileged=true --network=host --gpus all --name [给容器一个名字] accelsim/ubuntu-18.04_cuda-11

在A100本机上新开一个文件夹作为[要映射到容器内的A100路径]，然后对[容器内路径]地修改就会同步

apt-get install build-essential xutils-dev bison zlib1g-dev flex libglu1-mesa-dev
apt-get install doxygen graphviz
apt-get install python-pmw python-ply python-numpy libpng-dev python-matplotlib
apt-get install libxi-dev libxmu-dev freeglut3-dev

官网下载并安装cuda-11 toolkit

./cuda_10.2.89_440.33.01_linux.run --toolkit --silent --installpath=[要安装到的地址]

### profile环境

Nsight Systems用于分析应用程序的整体瓶颈，Nsight Compute是内核级的分析

https://blog.csdn.net/weixin_40653140/article/details/136238420是一个总体的介绍

在docker里和windows上分别下载安装最新的Nsight Compute

### 调试环境

CUDA-GDB[可以不用装]

https://zhuanlan.zhihu.com/p/688561144

## 参考资料

cuda编程权威指南

大规模并行处理器程序设计

CUDA-MODE (https://github.com/cuda-mode)

GEMM优化 (https://zhuanlan.zhihu.com/p/435908830)

cutlass-cute (https://github.com/NVIDIA/cutlass/blob/main/media/docs/cute/00_quickstart.md)

triton tutorial (https://github.com/triton-lang/triton/tree/main)