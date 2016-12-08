# NCCL 注释版

NCCL是Nvidia开发的，用于单机多GPU环境下的通信库。

介绍资料：https://devblogs.nvidia.com/parallelforall/fast-multi-gpu-collectives-nccl/

github：https://github.com/NVIDIA/nccl

##特点
* 支持多线程通信方式，也支持MPI下的多进程通信方式
* 支持单机任意数量的GPU通信
* 支持的通信：allreduce, allgather, reduce-scatter, reduce, broadcast

##原理概述
* 通信线路使用PCIe。GPU之间支持GPUDirect P2P时使用P2P，否则使用Pinned Host Memory存储拷贝数据来通信
* 使用环状算法优化通信时的吞吐效率

##使用建议
* 对于小数据量的通信，尽量合并在一起

##注释的基础版
commit 648e9fbb58813cda91e785201f5c631f1ed4ddaa

Date:   Mon Dec 5 18:06:24 2016 -0800

##注释状态
刚刚新建
