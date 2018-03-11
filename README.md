# 安装tensorflow

## 安装环境

- 系统：Ubuntu 16
- GPU：1070
- 安装方式：runfile

## 准备

- CUDA 9.0
- cudnn v7
- Python Anaconda 3.6
- The libcupti-dev library \
  `未安装成功`
  > Unable to locate package cuda-command-line-tools
  
  后直接采用 `sudo apt-get install libcupti-dev` 并且添加环境变量
  ```bash
  $ export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/extras/CUPTI/lib64
  ```

## pip安装
选择好所要安装的Python（区分系统自带的还是Anaconda的、Python2还是Python3）
``` bash
pip install tensorflow-gpu
```
## 验证安装是否成功

``` python
# Python
import tensorflow as tf
hello = tf.constant('Hello, TensorFlow!')
sess = tf.Session()
print(sess.run(hello))
```

### 问题

1.出现warning

> FutureWarning: Conversion of the second argument of issubdtype from `float` to `np.floating` is deprecated

使用 `pip install numpy==1.13.0` 解决

2.黑窗可以正常运行，但是pycharm不可以正常运行出现Error

> ImportError: libcublas.so.9.0: cannot open shared object file: No such file or directory 

查阅网上出现此问题应该是tensorflow版本和cuda版本不匹配，但是此处tensorflow1.6和cuda9.0是没有问题的 \
倒腾半天后不知道怎么就解决了（有可能是重启）


![installation success](./img/tensorflow.png)

