### 1.1 Ubuntu 介绍

Ubuntu（友帮拓、优般图、乌班图）是一个以桌面应用为主的开源 GNU/Linux 操作系统，Ubuntu 是基于 GNU/Linux，
支持 x86、amd64（即 x64）和 ppc 架构，由全球化的专业开发团队（Canonical Ltd）打造的。

Ubuntu 和 Centos 都是基于 GNU/Linux 内核的，因此基本使用和 Centos 是几乎一样的，它们的各种指令可以通用，在学习和使用 Ubuntu 的过程中，会发现各种操作指令在前面学习 CentOS 都使用过。只是界面和预安装的软件有所差别。

**Ubuntu下载地址**: [https://cn.ubuntu.com/download](https://cn.ubuntu.com/download)

**阿里源镜像下载地址**: [http://mirrors.aliyun.com/ubuntu-releases/](http://mirrors.aliyun.com/ubuntu-releases/)

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602184554.png" style="zoom:80%;" />

### 1.2 修改软件下载地址

#### 1.2.1 apt 基本介绍

apt 是 `Advanced Packaging Tool`的简称，是一款安装包管理工具。在 Ubuntu 下，可以使用 apt 命令进行软件包的安装、删除、清理等，类似于 Windows 中的360软件管理工具。

**原理如下**：

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602192406.png)

#### 1.2.2 替换默认的镜像源

1、寻找国内镜像源： [清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/)

2、备份Ubuntu 默认的源地址

```shell
sudo cp /etc/apt/sources.list /etc/apt/sources.list.backup
```

备份成功！！！

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602194352.png)

3、在终端的窗口输入下面的命令使用`gedit`工具进行软件镜像源的数据编辑。

```shell
sudo gedit /etc/apt/sources.list
```

在编辑前可以将`sources.list`文件内的内容清除后，将上面获取到的清华镜像软件的帮助内容复制粘贴到文件中。并保存退出。

```xml
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse

# 预发布软件源，不建议启用
# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-proposed main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-proposed main restricted universe multiverse
```

4、执行更新源命令：`sudo apt-get update`

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602195218.png" style="zoom:80%;" />

5、更新已安装的包：`sudo apt-get upgrade`

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602203733.png" style="zoom:80%;" />

#### 1.2.3 软件操作命令

| 相关命令                                 | 基本作用                               |
| ---------------------------------------- | -------------------------------------- |
| sudo apt-get update                      | 更新源                                 |
| sudo apt-get install package             | 安装包                                 |
| sudo apt-get remove package              | 删除安装包                             |
| sudo apt-cache search package            | 搜索软件包                             |
| sudo apt-get install package --reinstall | 重新安装包                             |
| sudo apt-cache show package              | 获取包的相关信息，如说明、大小、版本等 |
| sudo apt-get -f install                  | 修复安装                               |
| sudo apt-get remove package --purge      | 删除包，包括配置文件等                 |
| sudo apt-get build-dep package           | 安装相关的编译环境                     |
| sudo apt-get upgrade                     | 更新已安装的包                         |
| sudo apt-get dist-upgrade                | 升级系统                               |
| sudo apt-cache depends package           | 了解使用该包依赖那些包                 |
| sudo apt-cache rdepends package          | 查看该包被哪些包依赖                   |

#### 1.2.4 案例分析

1、使用 apt 完成安装和卸载 vim 软件，并查询 vim 软件的信息。

删除操作

```shell
sudo apt-get remove vim
```

安装操作

```shell
sudo apt-get install vim
```

获取软件信息

```shell
sudo apt-cache show vim
```

### 1.3 Ubuntu root 用户

#### 1.2.1 基本介绍

Ubuntu安装成功后，都是普通用户权限，并没有最高 root 权限，如果需要使用 root 权限的时候，通常都会在命令前面加上 `sudo` ，有的时候感觉很麻烦。

一般可以使用 `su 命令`来直接切换到 root 用户的，但是如果没有给 root 设置初始密码，就会抛出 `su : Authentication failure` 这样的问题。所以，我们只要给 root 用户设置一个初始密码就好了。

#### 1.2.2 给root用户设置密码并使用

1、输入`sudo passwd`命令，设定 `root `用户密码。

2、设定 root 密码成功后，输入`su` 命令，并输入刚才设定的` root `密码，就可以切换成` root` 了。提示符`$`代表一般用户，
提示符`#`代表 root 用户。

3、以后就可以使用`root` 用户了。

4、输入` exit 命令`，退出 `root` 并返回一般用户。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602210227.png" style="zoom:80%;" />

#### 1.2.3 永久更改主机名

1、修改配置文件 **vim /etc/hostname** 保存退出，重启系统！

```shell
sudo vim /etc/hostname
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602204951.png" style="zoom:80%;" />

2、执行命令`reboot`，重启系统。打开终端发现执行成功！！！

### 1.4 远程登录 Ubuntu

#### 1.4.1 ssh 基本介绍

1、SSH 为 Secure Shell 的缩写，由 IETF 的网络工作小组（Network Working Group）所制定，SSH 为建立在应用层和传输层基础上的安全协议。

2、使用 SSH 服务，需要安装相应的服务器和客户端。客户端和服务器的关系：如果A 机器想被 B 机器远程控制，那么A 机器需要安装 SSH 服务器，B 机器需要安装 SSH 客户端。和 CentOS 不一样，Ubuntu 默认没有安装 SSHD 服务(使用`netstat` 指令查看，端口未在监听中)，因次不能进行远程登录。

```shell
netstat -anp | more
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602210735.png" style="zoom:80%;" />

#### 1.4.2 安装 SSH 和启用

1、执行命令

```shell
sudo apt-get install openssh-server
```

2、执行上面指令后，在当前这台 Linux 上就安装了 SSH 服务端和客户端。

```shell
service sshd restart
```

执行上面的指令，就启动了 sshd 服务。会监听端口 22

3、查看是不是已经安装或启用了ssh服务。

```shell
ps -e |grep ssh
```

如果有sshd，证明已经装好了ssh-server并已启用。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602212926.png)

4、使用xshell登录，登录成功操作！！！

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602211828.png" style="zoom: 67%;" />

#### 1.4.3 安装vsftpd和启用

1、查看是否安装了 vsftpd

```shell
vsftpd --version 
```

2、如果没有安装，执行以下指令

```shell
sudo apt install vsftpd
```

3、启动服务

```shell
sudo service vsftpd restart
```

4、测试连接`Xftp6`，连接成功！！！！

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602215006.png" style="zoom:80%;" />

### 1.5 安装搜狗输入法

1、下载地址: [https://pinyin.sogou.com/linux/](https://pinyin.sogou.com/linux/)

2、通过xftp上传到`/home`目录。

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602222921.png)

3、安装fcitx框架

```shell
sudo apt install fcitx-bin
sudo apt-get install fcitx-table
```

4、安装输入法

```shell
 sudo dpkg -i sogoupinyin_2.4.0.3469_amd64.deb 
```

如果安装过程中提示缺少相关依赖，则执行如下命令解决

```shell\
sudo apt-get install -f
```

5、配置输入法

添加中文语言支持，打开 系统设置——区域和语言——管理已安装的语言——在“语言”tab下——点击“添加或删除语言”

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602225255.png" style="zoom:80%;" />

6、配置搜狗输入法

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602230658.png" style="zoom:80%;" />

7、执行`reboot`命令，搜狗输入法就能使用了！！！

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602230830.png)

