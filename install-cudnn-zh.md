# 安装Cudnn

> 参考文档 http://docs.nvidia.com/deeplearning/sdk/cudnn-install/index.html
>
> IDIA cuDNN是用于深度神经网络的GPU加速库。它强调性能、易用性和低内存开销。

1. 解压文件
2. 复制cudnn文件到CUDA工具包目录
``` bash
$ sudo cp cuda/include/cudnn.h /usr/local/cuda/include
$ sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
$ sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*
```

这样就可以了

