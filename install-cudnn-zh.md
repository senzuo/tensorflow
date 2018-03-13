# 安装 cuDNN

> 参考文档 http://docs.nvidia.com/deeplearning/sdk/cudnn-install/index.html
>
> NVIDIA cuDNN是用于深度神经网络的GPU加速库。它强调性能、易用性和低内存开销。

1. 准备文件 cudnn-9.0-linux-x64-v7.tgz
2. 点击Extract解压文件到当前目录
2. 打开终端输入以下命令,复制cudnn文件到CUDA工具包目录
``` bash
$ sudo cp cuda/include/cudnn.h /usr/local/cuda/include
$ sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
$ sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*
```
这样就可以了

