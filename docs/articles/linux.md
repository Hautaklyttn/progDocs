---
layout: default
---

[Back](../)  

&nbsp;

# Linux
---  

&nbsp;

### 1. Basics    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.1 History</font>](#ch1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.2 Directories Explained</font>](#ch1-2)  
 
&nbsp;

---  

&nbsp;

# Basics  

&nbsp; 

<a name="ch1-1"></a>
### 1.1 History

&nbsp;

... tbd ...

&nbsp; 

<a name="ch1-2"></a>
### 1.2 Directories Explained  

<font size="-1">&rarr; Info taken from <a href="https://www.youtube.com/watch?v=42iQKuQodW4">here.</a> Very good short video.</font>  

The directory structure is written down in the *Filesystem Hierarchy Standard* (FHS 3).

&nbsp;

![0c](../assets/pics/linux_directories.png)  

&nbsp;

&nbsp;

***/BIN* directory**  

![0c](../assets/pics/linux_bin.png)

- contains binaries/executables that are essential to the entire operating system (e.g. the *ls* command)
- you can run these commands on the command line at any time and place

&nbsp;

&nbsp;

***/SBIN* directory**  

![0c](../assets/pics/linux_sbin.png)

- contains essential executables for the super user (root)
- should only be used by the root user

&nbsp;

&nbsp;

***/LIB* directory**

![0c](../assets/pics/linux_lib.png)

- contains libraries used by both the */bin* and the */sbin* folder

&nbsp;

&nbsp;

***/USR/BIN* directory**

![0c](../assets/pics/linux_usr_bin.png)

- contains non-essential (for the operating system) installed binaries
- folder is intended for the user

&nbsp;

&nbsp;

***/USR/LOCAL/BIN* directory**

![0c](../assets/pics/linux_usr_local_bin.png)

- contains binaries that the user compiled manually locally
- directory to provide a safe place that won't conflict with SW installed by a system package manager

&nbsp;

&nbsp;

***/ETC* directory**

![0c](../assets/pics/linux_etc.png)  

- stands for *et cetera* or *editable text configuration*
- contains data files to customize the SW on your system
- contains mostly text-based config files to be modified in the editor

&nbsp;

&nbsp;

***/HOME/*\<name\> directory**

![0c](../assets/pics/linux_home.png)  

- contains a directory for every user registered at the system
- contains the files, configuration and SW for that user

&nbsp;

&nbsp;

***/BOOT* directory**

![0c](../assets/pics/linux_boot.png)  

- contains the files needed to boot the system (e.g. the Linux Kernel)

&nbsp;

&nbsp;

***/DEV* directory**

![0c](../assets/pics/linux_dev.png)  

- stands for *device files*
- here you can interface with HW or with drivers as if they were regular files
- one can create disk partitions here or interface the floppy drive

&nbsp;

&nbsp;

***/OPT* directory**

![0c](../assets/pics/linux_opt.png)

- contains optional or add-on SW
- one rarely interacts with this directory

&nbsp;

&nbsp;

***/VAR* directory**

![0c](../assets/pics/linux_var.png)

- contains variable files that are changed as the operating system is being used
- contains files like logs or cache files

&nbsp;

&nbsp;

***/TMP* directory**

![0c](../assets/pics/linux_tmp.png)

- contains temporary files that won't be persistent between reboots

&nbsp;

&nbsp;

***/PROC* directory**

![0c](../assets/pics/linux_proc.png)

- contains an illusionary file system that doesn't actually exist on disk
- is created in memory on the fly by the Linux Kernel to keep track of running processes