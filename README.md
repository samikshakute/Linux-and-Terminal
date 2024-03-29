# Documentation

#### Table of Contents:

| Sr. No. | Topic                      
|:-------:|:-------------:        
| 1       | <a href="https://samikshakute.github.io/Linux-and-Terminal/#what-is-linux">Documentation</a>      
| 2.     | <a href="https://samikshakute.github.io/Linux-and-Terminal/commands/">Commands</a>   
| 3.     | <a href="https://github.com/samikshakute/Linux-and-Terminal/tree/main/Bash%20Scripting">Bash Scripting</a>              

#### What is Linux?
Just like we have Windows and Mac, Linux is an operating system. It is free and open-source.
Linux is a fully multi-tasking, multi-user operating system, with built-in networking and service processes known as daemons.
Linux is developed by a loose confederation of developers from all over the world, collaborating over the Internet, with Linus Torvalds at the head. Technical skills and a desire to contribute are the only qualifications for participating.
The Linux community is a far-reaching ecosystem of developers, vendors, and users that supports and advances the Linux operating system.

In Linux, files are stored in a hierarchical filesystem, with the top node of the system being the root or simply "/".

**Note**: *Linux was inspired by UNIX, but it is not UNIX.*

There are three major distribution families within Linux: Red Hat, SUSE, and Debian. 

<img src="https://courses.edx.org/assets/courseware/v1/1d8c97abd237dcd44a5fe5464f6521ac/asset-v1:LinuxFoundationX+LFS101x+2T2021+type@asset+block/chapter01_The_Linux_Kernel_Distribution_Families_and_Individual_Distributions.png">

Some of the common terms used in Linux are kernel, distribution, boot loader, service, filesystem, desktop environment, and command line.
#### Kernel
The kernel is considered the brain of the Linux operating system. It controls the hardware and makes the hardware interact with the applications. An example of a kernel is the Linux kernel. The most recent Linux kernel, along with past Linux kernels, can be found at the <a href="https://kernel.org/">kernel.org</a> web site.

#### Distribution
A distribution also known as Distros is a collection of programs combined with the Linux kernel to make up a Linux-based operating system. Some common examples of a distribution are Red Hat Enterprise Linux, Fedora, Ubuntu, and Gentoo.

#### Boot Loader
The boot loader, as the name implies, is a program that boots the operating system. Two examples of a boot loader are GRUB and ISOLINUX.

#### Service
A service is a program that runs as a background process. Some examples of the service are httpd, nfsd, ntpd, ftpd and named.

#### File System
A filesystem is a method for storing and organizing files in Linux. Some examples of filesystems are ext3, ext4, FAT, XFS and Btrfs.

#### Desktop Environment
The desktop environment is a graphical user interface on top of the operating system. GNOME, KDE, Xfce and Fluxbox are some examples of the desktop environment.

#### Command line
The command line is an interface for typing commands on top of the operating system.

#### What is Terminal Emulator?
It is basically a program/application that will allow us to use the terminal in a graphical environment. </br>
Using terminal we can control our OS.

#### What is a shell?
A shell is a command line interface that will take all our commands as input. It interprets the commands and tells the OS what to do. Some of the commonly used shells are bash shell, bourne shell, c shell, korn shell, z shell, etc. </br>

Part of the terminal is known as Command Prompt.

#### Username and Hostname:
When we open our terminal we can see something like this: samiksha@samiksha-Inspiron-5570 </br>
Here, samiksha is the computer's username and samiksha-Inspiron-5570 is the host name.

#### What are environment variables?
These are named values that are used to change how the commands and processes are executed. 
A process is an instance of a running command.
  - Setting environment variables:
    - One way to set environmental variables in bash is using the `export` keyword </br>
    - For example: `export MY_PATH="Samiksha"`
    - These variables are not permanent. if we close the terminal it will be gone.
    - If we want to modify the PATH variable we can edit the .profile file using `vim .profile` command. Each path is separated by a colon(:).

#### What are aliases?
Aliases are shortcuts for long commands. To set aliases only for a session(not permanent), we can use the command: `alias <shortcut-name>=<command>`.<br>
We can set our custom aliases permanently by editing the .bashrc file.

#### Bash Files
Whenever we open the terminal, some commands are automatically executed to automate tasks and it is dependent on bash.
Some of the bash files are .bashrc, .profile, .bash_history, etc. These files are located in the home directory. They are hidden and we can list them using the `ls -a` command. if we want to see what lies in these files we can use the `cat` command. </br>
For example: `cat .bashrc` will display the contents of the .bashrc file.

#### Directories
Following are the directories commonly found in the Linux file system:
~~~
/home # home directories and files from users
/bin # user command binaries (cat, echo, etc.)
/sbin # system binaries (need sudo)
/usr # user 
/usr/bin # primary executables that system needs in order to run
/usr/local # programs installed just for that user
/lib # when executables in /bin need additional library files in order to run
/var # variable data (temporary)
/var/log # logs are stored here usually for 30 days
/var/log/syslog # system logs
/var/cache # cached data from programs
/opt # programs that install everything in one directory (not separated in /bin and /lib)
/etc # system wide configurations
/etc/fstab # controls how different filesystems are treated each time they are introduced to a system
/etc/hosts # used to translate hostnames to IP-addresses. 
/etc/hostname # name of the machine
/etc/sudoers # who can act as the super user (sudo)
/tmp # temporary location for running processes
/boot # do not touch - for booting the system
/dev # devices configurations like mouse and keyboard
/media # devices like CD or usb drive auto mounts here
/mnt # temporary mount points for additional filesystems
~~~
