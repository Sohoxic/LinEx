# Kernel-Module
**This is a simple Linux kernel module written in C programming language that lists all the currently running processes in the system and their corresponding states.**

## How to run the kernel code?

**1.** Execute the `make` command to create the `.ko` file along with other files.<br> [P.S: The makefile and the main.c file should be in the same directory(at the same directory level]

```
make  
```
  <img src="https://github.com/Sohoxic/Kernel-Module/blob/main/assets/images/make.png">

**2.** Insert module into the kernel using `insmod`.

```
sudo insmod make.ko
```

<img src="https://github.com/Sohoxic/Kernel-Module/blob/main/assets/images/insmod.png">

**3.** To check if the kernel module is inserted into the kernel at runtime execute the `lsmod` command(you can see the main module at the top.)

```
lsmod
```

<img src="https://github.com/Sohoxic/Kernel-Module/blob/main/assets/images/lsmod.png">

**4.** Execute `modinfo` command to display information about the kernel module.

```
modinfo main.ko
```

<img src="https://github.com/Sohoxic/Kernel-Module/blob/main/assets/images/modinfo.png">

**5.** `dmesg` is a useful command-line tool that provides a convenient way to access and analyze kernel messages, making it an important tool for system administration and troubleshooting in Linux/Unix systems.

```
sudo dmesg
```

<img src="https://github.com/Sohoxic/Kernel-Module/blob/main/assets/images/dmesg.png">


**6.** Now remove the kernel module from the kernel using `rmmod` and then using `lsmod` to view that the module is no longer part of the kernel. [P.S - Only check the first line after executing lsmod to see whether the kernel module name `main` is there or not.]

```
sudo rmmod main
```

<img src="https://github.com/Sohoxic/Kernel-Module/blob/main/assets/images/rmmod.png">






