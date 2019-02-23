# shell脚本

## 什么是shell;
一门编程语言。

有以下几种类型
Bourne Shell（/usr/bin/sh或/bin/sh）
Bourne Again Shell（/bin/bash） (bash shell,linux 默认支持的。)
C Shell（/usr/bin/csh）
K Shell（/usr/bin/ksh）
Shell for Root（/sbin/sh）


## man [command]

give users manual pages

## grep

 匹配制定条件

## 进程  管理

### px aux | grep xxx

1. ps : list all process status;
   1. a:show processes for all user
   2. u: Display the processes belonging to the specified usernames.
   3. x:also show processes not attached to a terminal

### kill

-s 制定发送信号

1. HUP 1 终端断线
2. INT 2 中断（同 Ctrl + C）
3. QUIT 3 退出（同 Ctrl + \）
4. TERM 15 终止
5. KILL 9 强制终止
6. CONT 18 继续（与 STOP 相反， fg/bg 命令）
7. STOP 19 暂停（同 Ctrl + Z）
8. SIGTERM 15

```shell
kill [-s] pid

// 默认 15：可能会被忽略
kill xxx

```

## 查询

### ls

-l:  
use a long listing format;
ls -l == ll

-a :

### tail

-f: follow;
-n number: last num lines

### find

`find / -type d -name gtwang`
`find . -name gtwang`
-type:
d:directory f：:file

### which

serach command name to get there real excute path

`which node`
/root/.nvm/versions/node/v9.11.1/bin/node

### whereis

serach binary, source and manual pages of commands in the Linux system
`whereis node`

/usr/bin/node /usr/local/bin/node /opt/node-v6.10.3-linux-x64/bin/node /root/.nvm/versions/node/v9.11.1/bin/node

## 权限相关

[chmod linux](https://chmodcommand.com/chmod-777/)
[chomod](http://www.runoob.com/linux/linux-comm-chmod.html)

chmod [选项][number or letter] file

chmod -R 777 ~/.pm2 = chmod -R a+rwx ~/.pm2
chmod -R 777 ~/.pm2 = chmod -R a+rwx ~/.pm2
chmod -R 744 ~/.Pm2 = chmod -R a+rwx,g-wx,o-wx ~/.pm2
-c 或——changes：效果类似“-v”参数，但仅回报更改的部分；
-f 或--quiet 或——silent：不显示错误信息；
-R 或——recursive：递归处理，将指令目录下的所有文件及子目录一并处理；
-v 或——verbose：显示指令执行过程；

-rw------- (600) 只有拥有者有读写权限。
-rw-r--r-- (644) 只有拥有者有读写权限；而属组用户和其他用户只有读权限。
-rwx------ (700) 只有拥有者有读、写、执行权限。
-rwxr-xr-xr (755) 拥有者有读、写、执行权限；而属组用户和其他用户只有读、执行权限。
-rwx--x--x (711) 拥有者有读、写、执行权限；而属组用户和其他用户只有执行权限。
-rw-rw-rw- (666) 所有用户都有文件读、写权限。
-rwxrwxrwx (777) 所有用户都有读、写、执行权限。

chmod+x: ogo+x; add permission to the other permissions that the file already has.

## user manager

### sudo

/etc/sudoers

act as like a root manager

### usermod

usermod -aG sudo username

### su : switch user

1. change to anther user
   `su`

2. change
   `su -` 1. provided his own default login environment, 2. ; he also lands into his default home directory.

### adduser and delete user

#### adduser

1. c

#### userdele

`userdel`

```shell
// 1. - This will delete the testaccount user from the /etc/passwd, /etc/group and /etc/shadow configuration files,
userdel testaccount


// 2. delete the user’s home directory or contents.

userdel -r testaccount

```

## 操作 (复制，移动)

### scp

scp source targetFolder
-r

`scp -r root@47.95.200.95:/etc/nginx /Users/fenglintang/Desktop`

### cp

### mv (move)

mv curretnfile (targetFile | targetfolder)

# ssh

1. 是什么?

>  安全协议，类似 https

2. 怎么用？
   ssh -v root@xxx.xxx
   ssh root@47.75.135.206

## create

### mkdir

-p : mkdir -p first/second/third;
If the first and second directories do not exist, due to the -p option, mkdir will create these directories for us.

## ssh 设置别名

```c
~/.ssh/config这个

# 服务器1
Host 别名
    HostName IP地址
    Port 22
    User 用户名
# 服务器2
Host 别名
    HostName IP地址
    Port 22
    User 用户名
更多的服务器...
```

## ssh git 配置

1. generate key
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

2. copy ssh key to

   1. copytoService: ssh-copy-id -i ~/.ssh/id_rsa.pub user@host
   2. copytogit

3. 测试 `ssh -T git@github.com`

# Ubuntu

## PPA

[什么是 Ubuntu PPA 以及为什么要用它[技术说明]](https://blog.csdn.net/Bobsweetie/article/details/50993516)
[在 Ubuntu 中添加和删除 PPA 的软件源
](https://blog.csdn.net/lu_embedded/article/details/55803500)

Ubuntu 提供的  应用开发市场, 

```shell
 add-apt-repository ppa:user/ppa-name
 apt-get update
 apt-get install xxxx
```

## install

```shell

// update package information; 没有实际更新软件
apt-update

apt-install <pack_age>

```



### 内存监控

内存监控
`free -h`

-buffers/cache 的内存数：95 (等于第 1 行的 used - buffers - cached)
+buffers/cache 的内存数: 32 (等于第 1 行的 free + buffers + cached)
可见-buffers/cache 反映的是被程序实实在在吃掉的内存，而+buffers/cache 反映的是可以挪用的内存总数。


# command

## grep
[grep](https://www.jianshu.com/p/9eb2edefecb7?from=singlemessage)
global search regular expression(RE) and print out the line




## ps 
[ps](https://www.tecmint.com/ps-command-examples-for-linux-process-monitoring/)
[ps-all](https://www.lifewire.com/uses-of-linux-ps-command-4058715)

process
`ps -ef | grep processname`

1. ps:list processes
2. -e: show all process 
3. -f - show processes in full format (more detailed than default)



### ps
it displays processes for the current shell.

### ps -A -e
Display every active process on a Linux system in generic (Unix/Linux) format.




### ps -ef
To perform a full-format listing, add the -f or -F flag.

The columns returned are as follows:
User ID
PID
PPID
C
STime
TTY
Time
Command


### ps aux
Display all processes in BSD format.




## find

```
find  path -type d -name "apt
```








