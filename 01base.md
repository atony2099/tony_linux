

# linux

[Linux/UNIX directories and shell commands for VARs](https://searchitchannel.techtarget.com/feature/Linux-UNIX-directories-and-shell-commands-for-VARs)
[前端&后端程序员必备的 Linux 基础知识](https://juejin.im/post/5b3b19856fb9a04fa42f8c71)


## 基础结构

![](http://ww1.sinaimg.cn/large/006dizvAly1g0glibj0xzj30a30870t4.jpg)

![](https://i1.wp.com/blog4jimmy.com/wp-content/uploads/2017/12/mmap2.png)


### 内核

主要职责:
1. 内存管理
2. 程序管理
3. 设备管理
4. 文件管理
![](http://ww1.sinaimg.cn/large/006dizvAly1g0glzt8qrpj30m60ew411.jpg)


### GNU工具


## 发行版本。
应用软件和内核构成了发行版本，也即是用户可以直接使用的linux系统
![](https://user-gold-cdn.xitu.io/2018/7/3/1645efa7048fd018?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)



## linux的文件系统
linux没有区分c盘 d盘；
把所有文件都放在同一个目录结构中。这个目录即是虚拟目录。


### directory base

![](http://www.debianadmin.com/images/ldr.png)

1. / is the root directory
2. /bin/ and /usr/bin/ store user commands.
3. /boot/ contains files used for system startup including the kernel.
4. /dev/ contains device files
5. /etc/ is where configuration files and directories are located.
6. /home/ is the default location for users‟ home directories.
7. /initrd/ is used to load required device modules and mount the initrd.img image file during system startup.
8. /lib/ and /usr/lib/ hold library files used by programs in /bin/ and /sbin/.
9. /lost+found/ holds orphaned files (files without names) found by fsck
10. /mnt/ holds the mount points for file systems that were mounted after boot.
11. /opt/ is used primarily for installation and unintallation of third-party software. Holds optional files and programs.
12. /proc/ is a virtual directory (not actually stored on the disk) which holds system information required by certain programs.
13. /root/ is the home directory of the superuser "root"
14. /sbin/ and /usr/sbin/ store system commands.
15. /tmp/ is the system temporary directory. All users have read+write access to /tmp/.
16. /usr/ contains files related to users such as application files and related library files ("usr" is an acronym that stands for UNIX system resources).
17. /var/ (as in "variable") holds files and directories that are constantly changing such as printer spools and log files.

`lsb -release --print distribution specific information`

### usr

Unix System Resource

1. /usr/bin 下面的都是系统预装的可执行程序
2. /usr/local/bin 目录是给用户放置自己的可执行程序的地方，推荐放在这里，不会被系统升级而覆盖同名文件。


