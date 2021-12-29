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

### 1.3 创建Ubuntu虚拟机

1、点击 文件 -> 新建虚拟机 创建一台新虚拟机

·![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100509.png)

2、在弹出框中选择典型安装

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602133203.png)

3、选择稍后安装系统

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100604.png)

4、选择引导系统是Linux并选择系统版本是CentOS

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602133318.png)

5、选择安装位置

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602133409.png)

6、确定磁盘的最大使用空间

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526100736.png)

7、设置网络适配器为NAT连接网络模式

- NAT英文全称是“Network Address Translation”，中文意思是“网络地址转换”，NAT 可以让内部网络连接到Internet或其它IP网络上。
- 虚拟机中的linux系统与windows主机形成一个局域网
- 并共享windows主机外网网络。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602133616.png)

### 1.4 安装Ubuntu20.04

1、开启虚拟机

<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602133918.png" style="zoom:80%;" />	

2、启动机器安装系统

<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602134048.png" style="zoom:80%;" />	

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602134142.png" style="zoom:80%;" />

3、选择最小安装，继续执行

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602134320.png)

4、点击安装位置，清除磁盘，然后进行自动分区。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602134618.png" style="zoom:80%;" />

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602134736.png" style="zoom:80%;" />

5、选择系统时区

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602134837.png)`

6、设置用户名和密码

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602135029.png" style="zoom:80%;" />

7、重新引导系统

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602135214.png)	

8、重启以后登录成功！！！

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602135522.png" style="zoom:80%;" />

