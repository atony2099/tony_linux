

# linux

[Linux/UNIX directories and shell commands for VARs](https://searchitchannel.techtarget.com/feature/Linux-UNIX-directories-and-shell-commands-for-VARs)
[前端&后端程序员必备的 Linux 基础知识](https://juejin.im/post/5b3b19856fb9a04fa42f8c71)


## linux内核。

  



## 操作系统

分为内核 和外核，
内核主要是和硬件打交道。
外核面向用户

而我们说的 linux 一般是指 linux 内核。

## 发行版本。

基于 linux 内核开发的
![](https://user-gold-cdn.xitu.io/2018/7/3/1645efa7048fd018?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

## directory

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

## usr

Unix System Resource

1. /usr/bin 下面的都是系统预装的可执行程序
2. /usr/local/bin 目录是给用户放置自己的可执行程序的地方，推荐放在这里，不会被系统升级而覆盖同名文件。

## 监控

### 内存监控

内存监控
`free -h`

-buffers/cache 的内存数：95 (等于第 1 行的 used - buffers - cached)
+buffers/cache 的内存数: 32 (等于第 1 行的 free + buffers + cached)
可见-buffers/cache 反映的是被程序实实在在吃掉的内存，而+buffers/cache 反映的是可以挪用的内存总数。
