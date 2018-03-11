# 安装cuda

# 安装前准备

确认有一个支持CUDA的GPU

``` bash
$ lspci | grep -i nvidia
# 01:00.0 VGA compatible controller: NVIDIA Corporation Device 1b81 (rev a1)
# 01:00.1 Audio device: NVIDIA Corporation Device 10f0 (rev a1)
```

确保系统有正确的内核header和安装开发包

``` bash Ubuntu
$ sudo apt-get install linux-headers-$(uname -r)
# 安装
```
选择安装方式 -> runfile安装

# Runfile 安装

> 参考文档
> http://docs.nvidia.com/cuda/cuda-quick-start-guide/index.html#ubuntu-x86_64-run


1. 禁用 Nouveau 驱动: 

    创建文件 /etc/modprobe.d/blacklist-nouveau.conf 文件内容为

``` bash
    blacklist nouveau
    options nouveau modeset=0
```

	重新生成 the kernel initramfs:
    
``` bash
$ sudo update-initramfs -u
```

2. 通过暂时在系统内核启动参数添加数字3重启进入级别3（text mode）
*此处使用了其他方法*
ps： 准备好runfile文件以及所在目录

	1. 重启电脑，在登录界面 Ctrl Alt F1 进入text mode 
	2. 命令行输入 `sudo service lightdm stop` 关闭GUI
	3. 切换到runfile目录
	4. 安装 `sudo sh cuda*.run`
	5. 返回GUI `sudo service lightdm start` + `ctrl alt f7`
	





# 安装后操作
1. mandatory actions
	1.1 env setup
	$ export PATH=/usr/local/cuda/bin${PATH:+:${PATH}}
	$ export LD_LIBRARY_PATH=/usr/local/cuda/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
