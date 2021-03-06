# Pre-installation Actions

Verify You Have a CUDA-Capable GPU

``` bash
$ lspci | grep -i nvidia
01:00.0 VGA compatible controller: NVIDIA Corporation Device 1b81 (rev a1)
01:00.1 Audio device: NVIDIA Corporation Device 10f0 (rev a1)
```

2.4. Verify the System has the Correct Kernel Headers and Development Packages Installed

``` bash Ubuntu
$ sudo apt-get install linux-headers-$(uname -r)

```

Choose an installation method -> *runfile*

# Runfile Installation

http://docs.nvidia.com/cuda/cuda-quick-start-guide/index.html#ubuntu-x86_64-run

1. Disable the Nouveau drivers: 

    Create a file at /etc/modprobe.d/blacklist-nouveau.conf with the following contents:
    Regenerate the kernel initramfs:

``` bash
    blacklist nouveau
    options nouveau modeset=0
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
