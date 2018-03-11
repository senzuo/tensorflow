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

2. Reboot into runlevel 3(No GUI) by temporarily adding the number "3" to the end of the system's kernel boot parameters.
	
	add para : https://askubuntu.com/questions/19486/how-do-i-add-a-kernel-boot-parameter

		grub menu: https://askubuntu.com/questions/16042/how-to-get-to-the-grub-menu-at-boot-time

3. Verify that the Nouveau drivers are not loaded.




# post installation
1. mandatory actions
	1.1 env setup
	$ export PATH=/usr/local/cuda/bin${PATH:+:${PATH}}
	$ export LD_LIBRARY_PATH=/usr/local/cuda/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
