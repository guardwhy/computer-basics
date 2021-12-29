### 1.1 虚拟机简介

虚拟机是一个软件，它可以使你在一台真实PC机器上同时运行两个或更多的操作系统，如：Windows或Linux。它可以模拟一个标准的PC环境，这个环境和真实的计算机一样，有芯片组、CPU、内存、显卡、声卡、网卡、软驱、硬盘、光驱、串口、并口、USB控制器。

1、目前市场上流行的虚拟机有两种：

- VMware（威睿）公司的虚拟机软件，功能强大，收费产品，有30天试用期。
- VirtualBox （甲骨文）公司的虚拟机软件，免费的商品。

2、VMware Workstation下载地址

- [https://www.vmware.com/cn.html](https://www.vmware.com/cn.html)
- [https://www.nocmd.com/windows/740.html](https://www.nocmd.com/windows/740.html)

3、VMware Workstation安装前步骤

- 去BIOS里面修改设置开启虚拟化设备支持(F2, F10)
- 在BIOS开启CPU虚拟化支持文档: [https://jingyan.baidu.com/article/ab0b56305f2882c15afa7dda.html](https://jingyan.baidu.com/article/ab0b56305f2882c15afa7dda.html)

### 1.2 VMware Workstation 安装

1、双击如下安装文件进行安装

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526095944.png)

2、出现欢迎界面

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100013.png)	

3、接受软件许可协议

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100048.png)	

4、选择安装目录

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100117.png)	

5、用户体验设置

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100142.png)	

6、创建快捷方式

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100210.png)	

7、开始复制文件

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100240.png)	

8、安装结束

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100308.png)	

9、安装完成，桌面就会启动图标，双击

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100334.png)	

10、第1次运行，如下图，输入注册码，或者试用30天

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100413.png)

11、可以使用了

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526102927.png)	



### 1.3 创建linux虚拟机

1、点击 文件 -> 新建虚拟机 创建一台新虚拟机

·![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100509.png)

2、在弹出框中选择典型安装

·![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100537.png)

3、选择稍后安装系统

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100604.png)

4、选择引导系统是Linux并选择系统版本是CentOS

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100648.png)

5、选择安装位置

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100716.png)

6、确定磁盘的最大使用空间

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100736.png)

7、准备安装前的硬件设置

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100803.png)

8、设置网络适配器为NAT连接网络模式

- NAT英文全称是“Network Address Translation”，中文意思是“网络地址转换”，NAT 可以让内部网络连接到Internet或其它IP网络上。
- 虚拟机中的linux系统与windows主机形成一个局域网
- 并共享windows主机外网网络。

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100832.png)	

### 1.4 安装CentOS 7.x

1、开启虚拟机

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602135713.png" style="zoom:80%;" />

2、启动机器安装系统

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100919.png)	

3、引导安装，点击next

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100940.png)

4、软件选择，选择"基本网页服务器"-> "开发工具和传统X Windows系统的兼容性"

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526092451.png)

5、点击安装位置

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526093510.png)

6、进行分区操作

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526093801.png)

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526093844.png)

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526093947.png)

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526094029.png)

6、关闭KDUMP

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526094208.png)

7、设置外网网卡打开

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526101051.png)

8、设置网卡自动连接

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526101114.png)

9、网络配置完成

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526101150.png)

10、配置完成，点开始安装系统

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526101215.png)

10、复制文件的过程中可以设置root管理员密码

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526101243.png)

11、密码设置为root，因为密码太短，点完成两次

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526101314.png)

12、创建普通用户
![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526094653.png)

·![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526094727.png)

13、重新引导系统

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526101355.png)	

### 1.5 用户登录和退出

root用户登录进入Linux 

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526101430.png)

root用户退出Linux 或logout

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526101453.png)

>  **命令提示符说明**

- 切换到超级用户: `sudo su`
- 退出超级用户: `exit`

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526101613.png)	

### 1.6 网络连接的模式

**桥接模式**

- 虚拟系统可以和外部系统通讯，但是容易造成IP冲突。

**NAT模式**

- 网络地址转换模式，虚拟系统可以和外部系统通讯，不造成IP冲突。

**主机模式**

- 独立的系统

###  1.7 安装 vmtools

vmtools 安装后可在 windows 下更好的管理 vm 虚拟机，可以设置 windows 和 linux 的共享文件夹。

> **安装 vmtools 的步骤**

1、进入 linux系统， 点击 vm 菜单的vmware tools安装，centos 会出现一个 vm 的安装包。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526120814.png" style="zoom:67%;" />

2、拷贝到 /opt目录，使用解压命令 tar, 得到一个安装文件。

<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526121007.png" style="zoom:67%;" />

3、进入该 vm 解压的目录 , opt 目录下进行解压。

```css
tar zxvf VMwareTools-10.3.23-17030940.tar.gz 
```

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526121810.png)

4、安装 ./vmware-install.pl

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526121629.png)

5、全部使用默认设置即可, 就可以安装成功！！

> **设置共享文件夹**

1、可以设置一个共享文件夹，比如 E:/Linux/Myshare。

2、点击 菜单==》虚拟机(vm) ==》设置

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526124733.png" style="zoom: 80%;" />

3、windows 和 linux 可共享E:/Linux/Myshare目录可以读写文件了

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526125124.png)

4、windows 和 linux可以共享文件，但是在实际开发中，文件的上传下载是需要使用远程方式完成的！！！

