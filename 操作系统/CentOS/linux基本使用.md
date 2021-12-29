## 1- linux目录结构

### 1.1 基本概念

- linux 的文件系统是采用级层式的树状目录结构，在此结构中的最上层是根目录“/”，然后在此目录下再创建其他的目录。
- 在 Linux 世界里，一切皆文件！！！

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526134130.png)

### 1.2 具体的目录结构

**/bin(/usr/bin /usr/local/bin)**

是 Binary 的缩写, 这个目录存放着最经常使用的命令。

**/sbin (/usr/sbin /usr/local/sbin)**
s就是 Super User 的意思，这里存放的是系统管理员使用的系统管理程序。

**/home [常用]**
存放普通用户的主目录，在 Linux 中每个用户都有一个自己的目录，一般该目录名是以用户的账号命名。

**/root [常用]**
该目录为系统管理员，也称作超级权限者的用户主目录

**/lib** 

系统开机所需要最基本的动态连接共享库，其作用类似于 Windows 里的 DLL 文件。几乎所有的应用程序都需要用到这些共享库

**/lost + found** 

这个目录一般情况下是空的，当系统非法关机后，这里就存放了一些文件。

**/etc [常用]**
所有的系统管理所需要的配置文件和子目录, 比如安装 mysql 数据库 my.conf

 **/usr [常用]**
这是一个非常重要的目录，用户的很多应用程序和文件都放在这个目录下，类似与 windows 下的 program files 目录。

/**boot[常用]** 

 存放的是启动 Linux 时使用的一些核心文件，包括一些连接文件以及镜像文件。

**/proc [不能动]**

 这个目录是一个虚拟的目录，它是系统内存的映射，访问这个目录来获取系统信息。

**/srv [不能动] **

service 缩写，该目录存放一些服务启动之后需要提取的数据。

**/sys[不能动]**

这是 linux2.6 内核的一个很大的变化，该目录下安装了 2.6 内核中新出现的一个文件系统 sysfs。

**/tmp** 

这个目录是用来存放一些临时文件的。

/**dev**
类似于 windows 的设备管理器，把所有的硬件用文件的形式存储。

**/media [常用]** 

linux 系统会自动识别一些设备，例如 U 盘、光驱等等，当识别后，linux 会把识别的设备挂载到这个目录下。

**/mnt [常用]**
系统提供该目录是为了让用户临时挂载别的文件系统的，可以将外部的存储挂载在/mnt/上，然后进入该目录就可以查看里的内容了。 d:/myshare

 **/opt** 

这是给主机额外安装软件所存放的目录。如安装 ORACLE 数据库就可放到该目录下，默认为空。

**/usr/local [常用]**
这是另一个给主机额外安装软件所安装的目录，一般是通过编译源码方式安装的程序。

**/var [常用]**
这个目录中存放着在不断扩充着的东西，习惯将经常被修改的目录放在这个目录下，包括各种日志文件。

> **文件不同颜色表示的含义**

| 颜色                                 | 说明                      |
| ------------------------------------ | ------------------------- |
| **白色**                             | 普通文件                  |
| <font color="blue">**深蓝色**</font> | 目录                      |
| <font color="red">**红色**</font>    | 压缩文件                  |
| <font color="00b7ee">**青色**</font> | 链接，类似windows快捷方式 |
| <font color="orange">**橙色**</font> | 设备文件                  |
| <font color='green'>**绿色**</font>  | 可执行文件                |

## 2- Vi 和 Vim 编辑器

### 2.1 基本介绍

Linux 系统会内置 vi 文本编辑器
Vim 具有程序编辑的能力，可以看做是 Vi 的增强版本，可以主动的以字体颜色辨别语法的正确性，方便程序设计。
代码补完、编译及错误跳转等方便编程的功能特别丰富，在程序员中被广泛使用。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526155003.png)

### 2.2 vi和vim常用的三种模式

基本上 vi/vim 共分为三种模式，分别是**命令模式（Command mode）**，**输入模式（Insert mode）**和**底线命令模式（Last line mode）**。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526155657.png)

| 操作模式 | 作用                                                         |
| -------- | ------------------------------------------------------------ |
| 命令模式 | 以 vim 打开一个档案就直接进入一般模式了(这是 默认的模式)。<br/>在这个模式中， 可以使用『上下左右』按键来移动光标，可以使用『删除字符』或『删除整行』来处理档案内容。<br/>也可以使用『复制、粘贴』来处理你的文件数据。 |
| 编辑模式 | 按下 i, I, o, O, a,A, r, R 等任何一个字母之后才会进入编辑模式, 一般来说按 i 即可。<br/>在此模式下可以输入字符，进行编辑等操作。 |
| 底行模式 | 输入 esc 再输入：在这个模式当中， 可以提供你相关指令，完成读取、存盘、替换、离开 vim <br/>显示行号等的动作则是在此模式中达成的。 |

### 2.3 vi 和 vim 基本使用

> **步骤一**

使用 vi 来建立一个名为 kobe.txt 的文件时

```shell
$ vim kobe.txt
```

直接输入 **vi 文件名** 就能够进入 vi 的一般模式了。请注意，记得 vi 后面一定要加文件名，不管该文件存在与否！

<img src="E:\学习笔记\linux\01-linux\07-vim\03-vim输入.jpg" style="zoom:80%;" />	

> **步骤二**

在一般模式之中，只要按下 ==i, o, a== 等字符就可以进入输入模式了！

在编辑模式当中，在左下角状态栏中==会出现 –INSERT- 的字样==，那就是可以输入任意字符的提示。键盘上除了 **Esc** 这个按键之外，其他的按键都可以视作为一般的输入按钮了。

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526155904.jpg)	

> **步骤三**

按下 ESC 按钮回到一般模式，存盘并离开的指令很简单，输入 `: wq` 即可保存离开！

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526155945.png)

### 2.4 vi 和 vim 快捷键

1、命令模式下按键

| **命令** | **描述**               |
| -------- | ---------------------- |
| **i**    | 在光标的前面插入字符   |
| **a**    | 在光标的后面添加入字符 |
| **o**    | 在光标下一行插入字符   |

2、命令模式下常用的编辑命令

| **命令**            | **描述**                                                |
| ------------------- | ------------------------------------------------------- |
| **yy**              | 复制当前行，拷贝当前行向下的 5 行 5yy，并粘贴（输入 p） |
| **p**               | 粘贴                                                    |
| **dd**              | 删除当前行                                              |
| **u**               | 撤销                                                    |
| **/字符串**         | 搜索字符串的内容<br />n： 查找下一个<br />N：查找前一个 |
| **:wq**             | write  quit 保存退出                                    |
| **:q!**             | 强制退出，不保存                                        |
| **:wq!**            | 强制保存退出，用于只读文件                              |
| set nu 和  set nonu | 设置文件的行号，取消文件的行号                          |

## 3- 用户基本操作

### 3.1 关机&重启命令

| 命令            | 作用                   |
| --------------- | ---------------------- |
| shutdown –h now | 立该进行关机           |
| shudown -h 1    | 1 分钟后会关机了       |
| halt 关机       | 作用和上面一样         |
| reboot          | 现在重新启动计算机     |
| sync            | 把内存的数据同步到磁盘 |

> 注意: 

不管是重启系统还是关闭系统，首先要运行` sync 命令`，把内存中的数据写到磁盘中。
目前的 shutdown/reboot/halt 等命令均已经在关机前进行了 sync 。

### 3.2 用户登录和注销

- ==登录时尽量少用 root 帐号登录，因为它是系统管理员，最大的权限，避免操作失误==。
- 可以利用普通用户登录，登录后再用`su - 用户名`命令来切换成系统管理员身份。
- 在提示符下输入 logout 即可注销用户。

### 3.3 普通用户和root用户切换

1、**[linux@guardwhy ~]$ ：linux表示当前用户，guardwhy表示主机名，$表示普通用户。 [root@guardwhy ~]#** ：root表示管理员用户,#表示在超级用户下输入命令。

2、输入命令： `su  - `,此时输入root用户的密码

```shell
su - :切换到超级用户
```

**图示：**
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020042511532199.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2h4eTE2MjUzMDk1OTI=,size_16,color_FFFFFF,t_70)


3、root用户切换成普通用户。

```shell
su - linux
```

4、普通用户重新切换成root用户。

```shell
输入命令:exit，直接切换成root用户，不在输入密码
```

​	![在这里插入图片描述](https://img-blog.csdnimg.cn/20200425115335667.jpg)

## 4 - Linux常用指令

### 4.1 指定运行级别

1、运行级别说明

- 常用运行级别是`3` 和 `5` ，也可以指定默认运行级别。
- `init [3]`, `init [5]`,通过`init`来切换不同的运行级别。

| 运行级别 | 说明                     |
| -------- | ------------------------ |
| 0        | 关机                     |
| 1        | 单用户【找回丢失密码】   |
| 2        | 多用户状态没有网络服务。 |
| 3        | 多用户状态有网络服务。   |
| 4        | 系统未使用保留给用户。   |
| 5        | 图形界面。               |
| 6        | 系统重启                 |

2、设置默认的运行级别

- centos7 进行了对级别运行进行了简化。

- 级别3：`multi-user.target: analogous to runlevel 3`
- 级别5：`graphical.target: analogous to runlevel 5`

==查看当前运行级别==

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527090651.png)

**设置运行级别**

```shell
systemctl set-default multi-user.target(运行级别3)
systemctl set-default graphical.target(运行级别5)
```

### 4.2 找回 root 密码

1、首先，启动系统，进入开机界面，在界面中按`e`进入编辑界面。如图

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527094230.png" style="zoom: 80%;" />

2、进入编辑界面，使用键盘上的上下键把光标往下移动，找到以`Linux16`开头内容所在的行数，在行的最后面输入`:init=/bin/sh`。

`<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527094417.png" style="zoom:80%;" />

3、接着，输入完成后，直接按快捷键：`Ctrl+x `进入单用户模式。

4、接着，在光标闪烁的位置中输入：`mount -o remount,rw /`(注意：各个单词间有空格)，完成后按键盘的回车键(Enter）。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527094706.png)

5、在新的一行最后面输入`passwd`， 完成后按键盘的回车键(Enter)。输入密码，然后再次确认密码即可，密码修改成功后，会显示passwd.....的样式，说明密码修改成功。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527094947.png)

6、 接着，在鼠标闪烁的位置中(最后一行中)输入：`touch /.autorelabel`(注意：touch与 /后面有一个空格)，完成后按键盘的回车键(Enter）

7、 继续在光标闪烁的位置中，输入`exec /sbin/init`（注意: exec与 /后面有一个空格），完成后按键盘的回车键(Enter）,等待系统自动修改密码完成后，系统会自动重启, 新的密码生效。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527095222.png" style="zoom:80%;" />

### 4.3 帮助指令

#### 4.3.1 man 指令

1、基本语法

```shell
基本语法：man [命令或配置文件]（功能描述：获得帮助信息）
```


在` linux` 下，隐藏文件是以 `.`开头 , 选项可以组合使用 比如` ls -al`, 比如 `ls -al /home`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527100600.png)

#### 4.3.2 help 指令

基本语法：`help` 命令(功能描述：获得 `shell` 内置命令的帮助信息）

**执行结果**

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527100816.png)

### 4.4 文件目录类

#### 4.4.1 pwd 指令

基本语法：`pwd` (功能描述: 显示当前工作目录的绝对路径)

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527101055.png)

#### 4.4.2 ls 指令

1、基本语法

| **语法：ls [参数]** | 功能说明list                                                 |
| ------------------- | ------------------------------------------------------------ |
| **无**              | 以简单的方式显示当前目录下所有的内容                         |
| **-l**              | 以详细的方式显示当前目录下所有的内容，简写为ll               |
| **-a**              | 显示所有的文件和目录，包含隐藏的文件。<br />注：在Linux中所有以点号开头的文件都是隐藏的 |

2、执行结果

<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527105211.png" style="zoom:80%;" />	

#### 4.4.3 cd指令

1、基本语法

| **cd** **目录名** | 说明                                                         |
| ----------------- | ------------------------------------------------------------ |
| **作用**          | Change Directory 改变目录                                    |
| **.**             | 当前目录，运行可执行文件的时候需要                           |
| **..**            | 上一级目录                                                   |
| -                 | 切换到上一个目录，相当于后退                                 |
| ~                 | 可以省略，切换到用户主目录<br />如果是管理员：切换到root目录，如果是普通用户：切换到home/用户名 |

2、操作演示

- 切换到系统根目录。
- 切换到该目录下`usr`目录。
- 切换到上一层目录。
- 切换到用户主目录，如果是`root`管理员，则是到`root`目录。
- 切换到上一个所在的目录。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527105949.png)

#### 4.4.4 mkdir指令

mkdir 指令用于创建目录

| **语法： mkdir[参数]** | 基本说明                  |
| ---------------------- | ------------------------- |
| 无                     | mkdir [选项] 要创建的目录 |
| -p                     | 创建多级目录              |

案例说明：

1、创建一个目录 /home/dog

```shell
mkdir /home/dog
```

2、创建多级目录 /home/animal/tiger

```shell
mkdir -p /home/animal/tiger
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527110736.jpg)

#### 4.4.5 rmdir指令

1、基本语法

指令删除空目录，如果需要删除非空目录，需要使用rm -rf 要删除的目录。

| **语法：rmdir[参数]** | 基本说明                                                    |
| --------------------- | ----------------------------------------------------------- |
| 无                    | rmdir [选项] 要删除的空目录，如果目录下有内容时无法删除的。 |

2、执行结果

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527111108.jpg)·

#### 4.4.6 touch 指令

1、touch 指令：创建空文件

```shell
touch hello.java
```

2、执行结果

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527113142.png)	

#### 4.4.7 cp 指令

1、基本语法

指令拷贝文件到指定目录。

| cp [选项] source dest | 基本说明             |
| --------------------- | -------------------- |
| `-r`                  | 递归复制整个文件夹。 |

2、案例说明

案例 1: 将` /home/hello.java` 拷贝到` /home/china` 目录下

```shell
cp hello.java /home/china
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527114919.png)


案例 2:  递归复制整个文件夹，比如将` /home/china` 整个目录，拷贝到` /opt`

```shell
cp -r /home/china /opt
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527120429.png" style="zoom:80%;" />

#### 4.4.8 rm指令

1、基本语法

`rm` 指令移除文件或目录

| **语法：rm  [参数]**  **文件或目录1** **文件或目录2** | 功能                                     |
| ----------------------------------------------------- | ---------------------------------------- |
| 无                                                    | 删除一个或多个文件或目录                 |
| `-r`                                                  | 删除整个目录树                           |
| `-f`                                                  | 删除前没有提示，默认删除前会有一个确认。 |

2、执行结果

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527120830.jpg)	

#### 4.4.9 mv 指令

1、基本语法

`mv` 移动文件与目录或重命名

| **mv**  **源目录**  **目标目录**  | 功能描述 |
| --------------------------------- | -------- |
| `mv oldNameFile newNameFile`      | 重命名   |
| `mv /temp/movefile /targetFolder` | 移动文件 |

案例说明：

将` /home/hello.java`文件 重新命名为 `spring.java`

```shell
mv hello.java spring.java
```

将 `/home/spring.java` 文件 移动到 `/root` 目录下

```shell
mv spring.java /root
```

移动整个目录 , 比如将` /opt/china` 移动到 `/home `下

```shell
mv china/ /home/
```

2、执行结果

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527130222.png" style="zoom:80%;" />

#### 4.4.10 cat 指令

1、基本语法

`cat` 查看文件内容，`cat `只能浏览文件，而不能修改文件，为了浏览方便，一般会带上 管道命令` | more`

| cat [选项] 要查看的文件 | 基本说明 |
| ----------------------- | -------- |
| `-n`                    | 显示行号 |

2、案例说明

/etc/profile 文件内容，并显示行号

```shell
cat -n /etc/profile | more 
```

3、执行结果

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527142825.png" style="zoom:80%;" />

#### 4.4.11 more 指令

1、基本语法

`more`指令是一个基于` VI `编辑器的文本过滤器，它以全屏幕的方式按页显示文本文件的内容，`more` 指令中内置了若干快捷键【交互的指令】

==操作说明==

| 操作            | 功能说明                              |
| --------------- | ------------------------------------- |
| 空白键`(space)` | 代表向下翻一页                        |
| `Enter`         | 代表向下翻一行                        |
| `q`             | 代表立刻离开`more`,不再显示该文件内容 |
| `Ctrl + F`      | 向下滚动一屏                          |
| `Ctrl + B`      | 返回上一屏幕                          |
| `=`             | 输出当前行的行号                      |
| `:f`            | 输出文件名和当前行的行号              |

2、案例说明

```shell
more /etc/profile
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527143556.png)

#### 4.4.12 less 指令

1、基本介绍

- `less`指令用来分屏查看文件内容，它的功能与 `more` 指令类似，但是比 `more` 指令更加强大，支持各种显示终端。
- `less`指令在显示文件内容时，并不是一次将整个文件加载之后才显示，而是根据显示需要加载内容，对于显示大型文件具有
  较高的效率。

==操作说明==

| 操作            | 功能说明                                             |
| --------------- | ---------------------------------------------------- |
| 空白键`(space)` | 代表向下翻一页                                       |
| `[pagedown]`    | 代表向下翻一行                                       |
| `[pageup]`      | 向上翻动一页                                         |
| `/`字串         | 向下搜索【字串】的功能，`n`：向下查找 ` N`：向上查找 |
| ？字串          | 向上搜索【字串】的功能，`n`：向上查找  `N`：向下查找 |
| `q`             | 离开`less`这个程序                                   |

#### 4.4.13 echo 指令

1、基本介绍

`echo` 输出内容到控制台

**基本语法**: `echo` [选项] [输出内容]

2、案例说明

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527144653.png)

#### 4.4.14 head 指令

1、基本介绍

head 用于显示文件的开头部分内容，默认情况下 head 指令显示文件的前 10 行内容

| head 指令      | 功能描述                              |
| -------------- | ------------------------------------- |
| head 文件      | 查看文件头 10 行内容                  |
| head -n 5 文件 | 查看文件头 5 行内容，5 可以是任意行数 |

2、案例: 查看/etc/profile 的前面 5 行代码

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527145322.png)

#### 4.4.15 tail 指令

1、基本介绍

`tail` 用于输出文件中尾部的内容，默认情况下 `tail` 指令显示文件的前 `10` 行内容。

| tail 指令        | 功能描述                                  |
| ---------------- | ----------------------------------------- |
| `tail` 文件      | 查看文件尾 `10 `行内容                    |
| `tail -n` 5 文件 | 查看文件尾 `5` 行内容，`5` 可以是任意行数 |

2、案例  查看/etc/profile 最后 5 行的代码

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527150200.png)

#### 4.4.16 > 指令 和 >> 指令

1、基本介绍

| > 指令 和 >> 指令         | 功能描述                                     |
| ------------------------- | -------------------------------------------- |
| `ls -l >`文件             | 列表的内容写入文件 `hello.java` 中【覆盖写】 |
| `ls -al >>`文件           | 列表的内容追加到文件`hello.java`的末尾       |
| `cat` 文件 `1 > `文件 `2` | 将文件 `1` 的内容覆盖到文件 `2`              |
| `echo` "内容"`>>` 文件    | 追加                                         |

2、案例说明

将 `/home` 目录下的文件列表 写入到 `/home/stu.yml `中, 覆盖写入。

```shell
ls -l /home > /home/mybatis.xml[如果mybatis.xml没有，则会创建]
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527164150.png" style="zoom: 80%;" />

将当前日历信息 追加到 `/home/mycal `文件中。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527164441.png" style="zoom:67%;" />

#### 4.4.17 ln指令

1、硬链接

- 只能创建指向文件的硬链接，不能创建指向目录。


2、软连接

- 可以指向文件或者目录,对于目录，一般都是用软链接。

- 软链接也称为符号链接，类似于 windows 里的快捷方式，主要存放了链接其他文件的路径。


| ln -s [原文件或目录] [软链接名] | 基本说明               |
| ------------------------------- | ---------------------- |
| 无                              | 给原文件创建一个软链接 |

3、应用实例

在`/home` 目录下创建一个软连接 `myroot`，连接到` /root `目录。

```shell
ln -s /root /home/myroot
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527171520.png" style="zoom: 80%;" />

删除软连接 `myroot`

```shell
rm /home/myroot
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527171748.png" style="zoom:80%;" />

### 4.5 时间日期类

#### 4.5.1 显示当前日期

1、基本介绍

| date指令                  | 功能描述         |
| ------------------------- | ---------------- |
| date                      | 显示当前时间     |
| date +%Y                  | 显示当前年份     |
| date +%m                  | 显示当前月份     |
| date +%d                  | 显示当前是哪一天 |
| date "+%Y-%m-%d %H:%M:%S" | 显示年月日时分秒 |

2、应用实例

显示当前时间信息

```shell
date
```

显示当前时间年月日

```shell
date "+%Y-%m-%d"
```

显示当前时间年月日时分秒

```shell
date "+%Y-%m-%d %H:%M:%S"
```

3、执行结果

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527175124.png)	

#### 4.5.2 设置日期

1、基本语法

```shell
date -s 字符串时间
```

2、应用实例

设置系统当前时间，比如设置成 `2021-05-27 20:02:10`

```shell
date -s “2021-05-27 20:02:10”
```

#### 4.5.3 cal 指令

1、基本语法

查看日历指令 cal

```css
cal [选项] 【功能描述：不加选项，显示本月日历】
```

2、应用实例

- 显示当前日历`cal`。
- 显示 `2020` 年日历 : `cal 2020`。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527175753.png" style="zoom:80%;" />

### 4.6 搜索查找类

#### 4.6.1 find 指令

`find` 指令将从指定目录向下递归地遍历其各个子目录，将满足条件的文件或者目录显示在终端。

**基本语法**：`find` [搜索范围] [选项]

| 选项说明           | 功能                             |
| ------------------ | -------------------------------- |
| `- name`<查询方式> | 按照指定的文件名查找模式查找文件 |
| `-user `<用户名>   | 查找属于指定用户名所有文件       |
| `-size`<文件大小>  | 按照指定的文件大小查找文件       |

 按文件名：根据名称查找/home 目录下的`mybatis.xml`文件

```shell
find /home -name mybatis.xml
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527214236.png)

#### 4.6.2  locate 指令

1、基本介绍

- `locate` 指令可以快速定位文件路径。
- `locate` 指令利用事先建立的系统中所有文件名称及路径的 locate 数据库实现快速定位给定的文件。
- `locate` 指令无需遍历整个文件系统，查询速度较快。为了保证查询结果的准确度，管理员必须定期更新 `locate`时刻。

**基本语法**：`locate` 搜索文件

**特别说明**：由于`locate`指令基于数据库进行查询，所以第一次运行前，必须使用`updatedb`指令创建locate数据库。

使用 `locate` 指令快速定位`mybatis.xml`文件所在目录

```shell
updatedblocate mybatis.xml
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527215604.png)

2、`which` 指令，可以查看某个指令在哪个目录下，比如` ls `指令在哪个目录。

```shell
which ls
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210527220116.png)

#### 4.6.3 grep 指令和 管道符号 |

1、基本介绍

`grep` 过滤查找，管道符，`|`表示将前一个命令的处理结果输出传递给后面的命令处理。

| grep [选项] 查找内容 源文件 | 功能描述           |
| --------------------------- | ------------------ |
| `-n`                        | 显示匹配行及其行号 |
| `-i`                        | 忽略字母大小写     |

2、应用实例

 请在 `hello.java` 文件中，查找 `Hello` 所在行，并且显示行号

方式一

```shell
cat /home/hello.java | grep -n "Hello"
```

方式二

```shell
grep -n "Hello" /home/hello.java
```

执行结果

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528083109.png" style="zoom:80%;" />

### 4.7 压缩和解压类

#### 4.7.1 gzip/gunzip 指令

1、基本介绍

`gzip` 用于压缩文件，` gunzip` 用于解压的。

| 源文件             | 功能描述                              |
| ------------------ | ------------------------------------- |
| `gzip` 文件        | 压缩文件，只能将文件压缩为`*.gz `文件 |
| `gunzip `文件`.gz` | 解压缩文件命令                        |

2、应用实例

 `gzip` 压缩， 将 `/home` 下的 `hello.txt` 文件进行压缩

```shell
gzip /home/hello.java
```

`gunzip` 压缩， 将 `/home` 下的 `hello.txt.gz` 文件进行解压缩

```shell
gunzip /home/hello.java.gz
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528094202.png)

#### 4.7.2  zip/unzip 指令

zip 用于压缩文件， unzip 用于解压的

> **基本语法**

`zip [选项] XXX.zip` 将要压缩的内容(功能描述：压缩文件和目录的命令）
`unzip [选项] XXX.zip` (功能描述：解压缩文件）

> **zip 常用选项**

-r：递归压缩，即压缩目录

> **unzip 的常用选项**

-d<目录> ：指定解压后文件的存放目录

应用实例

1、将 /home下的 所有文件/文件夹进行压缩成`myJava.zip`，将 home 目录及其包含的文件和子文件夹都压缩。

```shell
zip -r myJava.zip /home/
```

2、将 myJava.zip 解压到 /opt/tmp 目录下

```shell
mkdir /opt/tmpunzip -d /opt/tmp /home/myJava.zip
```

#### 4.7.3 tar 指令

1、基本介绍

`tar` 指令是打包指令，最后打包后的文件是 `.tar.gz` 的文件。

| 扩展名       | 分类                                                         |
| ------------ | ------------------------------------------------------------ |
| `.zip或.rar` | `windows`下压缩文件                                          |
| `.tar`       | `Linux`下打包文件，将多个文件打包成一个文件，文件没有压缩，反而会变大。 |
| `.gz`        | `Linux`下压缩文件，文件通常会变小                            |
| `.tar.gz`    | 既打包又压缩，比较常用的格式                                 |

**打包并压缩文件** ：`tar` [参数]压缩包名 一个或多被打包的文件。

| 参数              | 功能                                             |
| ----------------- | ------------------------------------------------ |
| `-c`              | `create` 创建一个压缩包文件                      |
| `-v`              | 显示压缩文件的详情                               |
| `-z`              | 压缩，如果没有这个参数，文件只是打包，并没有压缩 |
| `-f <压缩文件名>` | `file` 注：这个参数后面必须跟压缩的文件名        |

**解压文件**：`tar `[参数]解压文件到当前目录下


| 参数           | 功能         |
| -------------- | ------------ |
| `-x`           | 解压文件     |
| `-v`           | 显示详情     |
| `-f<压缩文件>` | 指定压缩文件 |
| `-z`           | 压缩         |

2、案例说明

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528114022.jpg)

### 4.8 其他命令

1、关机指令

- `shutdown -h now` : 表示立即关机
- `shutdown -h 1` : 表示 `1` 分钟后关机
- `halt`: 关机

2、重启指令

- `shutdown -r now`:  立即重启
- `reboot`：重启系统

3、用户登录和注销指令

- su -用户名：登录用户
- logout：注销用户

4、查看历史命令

- history

5、实用的快捷键

- `ctrl + w `: 删除光标左侧的一个单词。
- `ctrl + U` : 删除所有在光标左侧的命令字符。
- `ctrl + k` : 删除所有在光标右侧的命令字符。
- `ctrl + D` : 给终端传递`EOF`【文件结束符】。
- `Shift + PgUp` : 用于向上滚屏，与鼠标的滚轮向上滚屏是一个效果。
- `Shift + PgDn` : 用于向下滚屏，与鼠标的滚轮向下滚屏是一个效果。
- `Ctrl + A `: 光标跳到一行命令的开头，`Home`键有相同的效果。
- `Ctrl + E `: 光标跳到一行命令的结尾，`End`键有相同的效果。

6、清除命令

- `clear`，`Ctrl+L `用于清理终端的内容，跟`clear`命令一样的作用。

7、`top`指令

`top` 显示当前系统正在执行的命令情况，执行以后进入一个监控状态。每过`1`秒刷新一次。按`q`：才能退出命令。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528114627.png)

## 5- Linux用户管理

### 5.1 基本介绍

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526190949.png)

Linux 系统是一个多用户多任务的操作系统，任何一个要使用系统资源的用户，都必须首先向系统管理员申请一个账号，然后以这个账号的身份进入系统。 

### 5.2  添加用户

#### 5.2.1 基本语法

```shell
useradd 用户名
```

#### 5.2.2 应用案例

添加一个用户 `james`, 默认该用户的家目录在 `/home/james`

**注意事项**

- 当创建用户成功后，会自动的创建和用户同名的家目录。
- 也可以通过 useradd -d 指定目录 新的用户名，给新创建的用户指定家目录。

**执行结果**

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526191533.png)

### 5.3 指定/修改密码

#### 5.3.1 基本语法

```shell
passwd 用户名
```

#### 5.3.2 应用案例

给用户`james`指定密码，显示当前用户所在的目录 指令: `pwd`

```shell
passwd james
```

**执行结果**

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526192333.png)

### 5.4 删除用户

#### 5.4.1 基本语法

```shell
userdel 用户名
```

#### 5.4.2 应用案例

- 删除用户`james`，但是要保留家目录, `userdel james`。
- 删除用户以及用户主目录, 比如 `kobe, userdel -r kobe`。

==注意细节: 一般情况下，我们建议保留家目录==。

**执行结果**

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526193355.png)

### 5.5 查询用户信息指令

#### 5.5.1 基本语法

```shell
id 用户名
```

#### 5.5.2 应用案例

请查询 `guardwhy` 的信息，当用户不存在时，返回无此用户。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526193731.png)

#### 5.5.3 查看当前用户/登录用户

**基本语法**

```shell
当前用户: whoami
登录用户: who am I
```

**执行结果**

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526194355.png)

### 5.6 用户组

#### 5.6.1 基本介绍

用户组类似于角色，系统可以对有共性/权限的多个用户进行统一的管理。

#### 5.6.2 新增用户组

**基本指令**: `groupadd 组名`

#### 5.6.3 删除用户组

**基本指令**： `groupdel 组名`

**执行结果**

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526202815.png)

> **应用案例**

增加用户时直接加上组，指令(基本语法) : `useradd –g 用户组 用户名`，增加一个用`curry`, 直接将他指定到 `USA`组。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526203756.png)

#### 5.6.4 修改用户的组

**基本指令**：`usermod –g 组 用户组 用户名`

**案例演示**

创建一个组 CHINA，把 curry 放入到 CHINA
指令: `usermod -g CHINA curry`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526210633.png)

#### 5.6.5 用户和组相关文件

> **/etc/passwd 文件**

用户（user）的配置文件，记录用户的各种信息。
每行的含义：用户名:口令:用户标识号:组标识号:注释性描述:主目录:登录 Shell

```shell
vim /etc/passwd
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526211221.png)

> **/etc/shadow 文件**

口令的配置文件
每行的含义：登录名:加密口令:最后一次修改时间:最小时间间隔:最大时间间隔:警告时间:不活动时间:失效时间:标志。

```shell
vim /etc/shadow
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526211511.png)

> **/etc/group 文件**

- 组`(group)`的配置文件，记录 `Linux` 包含的组的信息。
- ==每行含义：组名:口令:组标识号:组内用户列表==。

```shell
vim /etc/group
```

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210526211709.png)	

## 6-linux组管理和权限管理

### 6.1 Linux 组基本介绍

在 linux 中的每个用户必须属于一个组，不能独立于组外。在 linux 中每个文件有==所有者、所在组、其它组==的概念

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528154346.png)

### 6.2 文件/目录 所有者

一般为文件的创建者,谁创建了该文件，就自然的成为该文件的所有者。

#### 6.2.1 查看文件所有者

指令：`ls -ahl`

**查看结果**

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528154919.png)

#### 6.2.2 修改文件所有者

指令：`chown 用户名 文件名`

**案例说明**

使用 root 创建一个文件 `test1.txt` ，然后将其所有者修改成 `curry`

```shell
chown curry test1.txt
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528155830.png)

### 6.3 组的创建

#### 6.3.1 基本指令

`groupadd` 组名

#### 6.3.2 应用实例

1、创建一个组`china`

```shell
groupadd china
```

2、创建一个用户 `yaoMing` ，并放入到`china`组中

```shell
useradd -g china yaoMing
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528161825.png)

### 6.4 文件/目录 所在组

当某个用户创建了一个文件后，这个文件的所在组就是该用户所在的组(默认)。

#### 6.4.1 查看文件/目录所在组

基本指令: `ls –ahl`

使用`yaoMing`来创建一个文件，看看该文件属于哪个组?

```shell
touch test02.txt
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528162809.png)

#### 6.4.2 修改文件/目录所在组

基本指令: `chgrp` 组名 文件名

**应用实例**

使用 root 用户创建文件`kobe.txt`,看看当前这个文件属于哪个组，然后将这个文件所在组，修改到`USA`组。

```shell
groupadd USA
touch kobe.txt
chgrp USA kobe.txt
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528164612.png)

### 6.5 其它组

除文件的所有者和所在组的用户外，系统的其它用户都是文件的其它组。

### 6.6 改变用户所在组

在添加用户时，可以指定将该用户添加到哪个组中，同样的用 root 的管理权限可以改变某个用户所在的组。

#### 6.6.1 改变用户所在组

`usermod –g` 新组名 用户名
`usermod –d` 目录名 用户名 改变该用户登陆的初始目录。 特别说明：用户需要有进入到新目录的权限。

#### 6.6.2 应用实例

将`james`这个用户从原来所在组，修改到`USA`组

1、查看所有的用户组

```shell
cat /etc/group
```

2、查看`james`用户所在组

```shell
id james
```

3、修改到`USA`组

```shell
usermod -g USA james
```

**执行结果**

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528180016.png)

### 6.7 权限的基本介绍

`ls -l`中显示的内容如下

```shell
-rwxrw-r-- 1 root root 1213 5月 27 09:39 hello.java
```

**0-9 位说明**

1、第 `0` 位确定文件类型(`d`, `-` , `l `, `c` , `b`)

- `l ` 是链接，相当于 `windows`  的快捷方式。
- `d ` 是目录，相当于 `windows`  的文件夹。
- `c`  是字符设备文件，鼠标，键盘。

```shell
cd /dev
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528214658.png)

- b 是块设备，比如硬盘。

```shell
cd /dev
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210528214500.png)

2、第 `1-3` 位确定 所有者（该文件的所有者）拥有该文件的权限。---`User`

3、第` 4-6` 位确定 所属组（同用户组的）拥有该文件的权限。---`Group`

4、第 `7-9` 位确定其他用户拥有该文件的权限。 ---`Other`

### 6.8 rwx 权限详解

#### 6.8.1 rwx 作用到文件

- `[ r ]`代表可读`(read)`: 可以读取,查看。
- `[ w ]`代表可写`(write)`: 可以修改,但是不代表可以删除该文件,删除一个文件的前提条件是对该文件所在的目录有写权限，才能删除该文件。
- `[ x ]`代表可执行`(execute)`:可以被执行。

#### 6.8.2 rwx 作用到目录

- `[ r ]`代表可读`(read)`: 可以读取，`ls` 查看目录内容。
- `[ w ]`代表可写`(write)`: 可以修改, 对目录内创建 + 删除 + 重命名目录。
- `[ x ]`代表可执行`(execute)`:可以进入该目录。

#### 6.8.3 文件及目录权限

`ls -l`中显示的内容如下

```shell
-rwxrw-r-- 1 root root 1213 5月 27 09:39 hello.java
```

1、10 个字符确定不同用户能对文件干什么？

- 第一个字符代表文件类型：`- l d c b`
- 其余字符每 3 个一组`(rwx) `读`(r)` 写`(w) `执行`(x)`
- 第一组 `rwx` : 文件拥有者的权限是读、写和执行。
- 第二组 `rw-` : 与文件拥有者同一组的用户的权限是读、写但不能执行。
- 第三组 `r-- `: 不与文件拥有者同组的其他用户的权限是读不能写和执行。

2、可用数字表示为: `r=4,w=2,x=1` 因此 `rwx=4+2+1=7` , 数字可以进行组合。

3、其它说明

- `1 `文件：硬连接数或 目录：子目录数。
- `root`  	用户
- `root` 	组
- `1213 `	文件大小(字节)，如果是文件夹，显示` 4096` 字节。
- `5`月 `27 09:39`  最后修改日期。
- `hello.java`	文件名。

### 6.9 修改权限-chmod

#### 6.9.1 基本说明

通过`chmod`指令，可以==修改文件==或者==目录==的权限。

#### 6.9.2 通过运算符变更权限

1、`u:所有者` `g:所有组` `o:其他人` `a:所有人(u、g、o 的总和)`

- `chmod u=rwx,g=rx,o=x` 文件/目录名。
- `chmod o+w` 文件/目录名。
- `chmod a-x` 文件/目录名。

2、案例演示

给 `abc.txt`文件 的所有者读写执行的权限，给所在组读执行权限，给其它组读执行权限。

```shell
chmod u=rwx,g=rx,o=rx abc.txt
```

给 `abc.txt` 文件的所有者除去执行的权限，增加组写的权限。

```shell
chmod u-x,g+w abc.txt
```

给 `abc.txt`文件的所有用户添加读的权限。

```shell
chmod a+r abc
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529092424.png" style="zoom:80%;" />

#### 6.9.3 通过数字变更权限

1、`chmod u=rwx,g=rx,o=x`文件目录名，相当于`chmod 751`文件/目录名。

- `x=1`，`w=2` , `wx = 3`, `r = 4`, `rx = 5`, `rw = 6`, `rwx = 7`

2、案例演示
将 `/home/abc.txt` 文件的权限修改成 rwxr-xr-x, 使用给数字的方式实现

```shell
chmod 755 /home/abc.txt
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529094101.png)

### 6.10 修改文件所有者-chown

#### 6.10.1 基本介绍

| 基本语法                             | 作用说明                                                     |
| ------------------------------------ | ------------------------------------------------------------ |
| `chown newowner` 文件/目录           | 改变所有者。                                                 |
| `chown newowner: newgroup` 文件/目录 | 改变所有者和所在组。<br/>**-R** 如果是目录 则使其下所有子文件或目录递归生效。 |

#### 6.10.2  案例演示

1、将 `/home/abc.txt` 文件的所有者修改成 `james`

```shell
chown james /home/abc.txt
```

2、将 `/home/Java	` 目录下所有的文件和目录的所有者都修改成 `james`

```shell
chown -R james /home/Java
```

3、执行结果

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529110038.png" style="zoom:80%;" />

### 6.11 修改文件/目录所在组

#### 6.11.1 基本介绍

`chgrp newgroup` 文件/目录 【 改变所在组】

#### 6.11.2 案例演示

1、请将 `/home/abc .txt` 文件的所在组修改成 `Dev`

```shell
groupadd Devchgrp Dev /home/abc.txt
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529111059.png" style="zoom:80%;" />

2、请将 `/home/Java`目录下所有的文件和目录的所在组都修改成`Dev`。

```shell
chgrp -R Dev /home/Java
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529111726.png)

## 7-Linux定时任务调度

### 7.1 crond 任务调度

`crontab` 进行定时任务的设置

#### 7.1.1 基本概述

- **任务调度**：是指系统在某个时间执行的特定的命令或程序。
- **任务调度分类**：1.系统工作：有些重要的工作必须周而复始地执行，如病毒扫描等。
- **个别用户工作**：个别用户可能希望执行某些程序，比如对 `mysql` 数据库的备份。

图解说明

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529143202.png" style="zoom:80%;" />

#### 7.1.2 基本语法

| crontab [选项] | 具体作用                        |
| -------------- | ------------------------------- |
| `- e`          | 编辑`crontab`定时任务           |
| `- l`          | 查询`crontab`任务               |
| `- r`          | 删除当前用户所有的`crontab`任务 |

#### 7.1.3 快速入门

1、设置任务调度文件：`/etc/crontab`，设置个人任务调度执行 `crontab –e`命令。

2、接着输入任务到调度文件，每小时的每分钟执行 `ls –l /etc/ > /tmp/b.txt` 命令。

```shell
*/1 * * * * ls –l /etc/ > /tmp/b.txt
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529153520.png)

> **参数细节说明**

1、5个占位符的说明

| 项目      | 含义                 | 基本范围              |
| --------- | -------------------- | --------------------- |
| 第1个 “*” | 一小时当中的第几分钟 | 0-59                  |
| 第2个 “*” | 一天当中的第几小时   | 0-23                  |
| 第3个 “*” | 一个月当中的第几天   | 1-31                  |
| 第4个 “*” | 一年当中的第几月     | 1-12                  |
| 第5个 “*” | 一周当中的星期几     | 0-7(0和7都代表星期日) |

2、特殊符号的说明

| 特殊符号 | 基本意义                                                     |
| -------- | ------------------------------------------------------------ |
| *        | 代表任何时间，比如第一个`*`就代表一小时中的每分钟都执行一次的意思。 |
| ，       | 代表不连续的时间，比如`0,8,12,16***命令`，就代表在每天的8点0分，12点0分，16点0分都执行一次命令。 |
| -        | 代表连续的时间范围。比如`0 5 ** 1-6命令`，代表在周一到周六的凌晨5点0分执行命令。 |
| */n      | 代表每隔多久执行一次，比如`*/10****命令`,代表每隔10分钟就会被执行一遍命令。 |

3、特殊时间执行案例

| 时间              | 含义                                                         |
| ----------------- | ------------------------------------------------------------ |
| 45 22 *** 命令    | 在22点45分执行命令                                           |
| 0 17 ** 1命令     | 每周1的17点0分执行命令                                       |
| 0 5 1,15 ** 命令  | 每月1号和15号的凌晨5点0分执行命令                            |
| 40 4 ** 1-5 命令  | 每周一到周五的凌晨4点40分执行命令                            |
| * /10 4 ** 命令   | 每天的凌晨4点，每隔10分钟执行一次命令                        |
| 0 0 1,15 * 1 命令 | 每月1号和15号，每周1的0点0分都会执行命令。<br/>注意: 星期几和几号最好不要同时出现，因为他们定义的都是天数，可能会让管理员出现混乱！！！ |

#### 7.1.4 应用案例

每隔 1 分钟， 将当前日期和日历都追加到 `/home/mycal` 文件中.

1、创建`my.sh`脚本，写入内容

```sh
date >> /home/mycal
cal >> /home/mycal
```

2、给 `my.sh`增加执行权限

```sh
chmod u+x /home/my.sh
```

3、 `crontab -e `，增加`*/1 * * * * /home/my.sh`

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529174129.png" style="zoom: 80%;" />

#### 7.1.5 crond 相关指令

1、基本介绍

`conrtab -r`：终止任务调度。
`crontab -l`：列出当前有那些任务调度。
`service crond restart` [重启任务调度]。

2、案例演示

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529174948.png)

### 7.2 at 定时任务

#### 7.2.1 基本介绍

1、`at 命令`是一次性定时计划任务，at 的守护进程 atd 会以后台模式运行，检查作业队列来运行。

2、默认情况下，atd 守护进程每 60 秒检查作业队列，有作业时，会检查作业运行时间，如果时间与当前时间匹配，则运行此作业。

3、`at 命令`是一次性定时计划任务，执行完一个任务后不再执行此任务了。

4、在使用 at 命令的时候，一定要保证 atd 进程的启动 , 可以使用相关指令来查看`ps -ef | grep atd`可以检测 atd 是否在运行。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529183453.png)

#### 7.2.2 定时任务示意图

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529184740.png" style="zoom:80%;" />

#### 7.2.3 at 相关组件

1、 at 命令格式

`at [选项] [时间]`
`Ctrl + D `结束 at 命令的输入， 输出两次。

2、at 命令选项

| 选项            | 含义                                                         |
| --------------- | ------------------------------------------------------------ |
| `- m`           | 当指定的任务被完成后，将给用户发送邮件，即使没有标准输出！！ |
| `- I`           | `atq`的别名                                                  |
| `- d`           | atrm的别名                                                   |
| `- v`           | 显示任务将被执行的时间                                       |
| `- c`           | 打印任务的内容到标准输出                                     |
| `- V`           | 显示版本信息                                                 |
| `-q `<队列>     | 使用指定的队列                                               |
| `-f` <文件>     | 从指定文件读入任务而不是从标准输入读入。                     |
| `- t`<时间参数> | 以时间参数的形式提交要运行的任务！！                         |

3、at 时间定义

- [ ] 接受在当天的 `hh:mm`(小时:分钟）式的时间指定。假如该时间已过去，那么就放在第二天执行，例如：`04:00`。
- [ ] 使用 `midnight`(深夜），`noon`(中午），`teatime`(饮茶时间，一般是下午 4 点）等比较模糊的词语来指定时间。
- [ ] 采用` 12` 小时计时制，即在时间后面加上 `AM`（上午）或 `PM`（下午）来说明是上午还是下午，例如：`12pm`。
- [ ] 指定命令执行的具体日期，指定格式为 `month day`（月 日）或 `mm/dd/yy`（月/日/年）或 `dd.mm.yy`（日.月.年），指定的日期必须跟在指定时间的后面。 例如：`04:00 2021-03-1`。
- [ ] 使用相对计时法。指定格式为：`now + count time-units` ，`now` 就是当前时间，`time-units` 是时间单位，这里能够是 `minutes`(分钟）、`hours`（小时）、`days`（天）、`weeks`（星期）。`count` 是时间的数量，几天，几小时。 例如：`now + 5 minutes`
- [ ] 直接使用 `today`(今天）、`tomorrow`(明天）来指定完成命令的时间。

#### 7.2.4 应用实例

1、1天后的上午8点执行 `/bin/ls /home`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529200336.png)

2、`atq` 命令来查看系统中没有执行的工作任务

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529200740.png)

3、明天16点整，输出时间到指定文件内。比如 /home/abc.log

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529201227.png)

4、删除已经设置的任务 , `atrm 编号`！！！

```shell
atrm 1 //表示将 job 队列，编号为 1 的 job 删除.
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529201547.png)

## 8-Linux磁盘分区和挂载

### 8.1 Linux 分区

#### 8.1.1 基本介绍

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530103132.png" style="zoom:80%;" />

- Linux 来说无论有几个分区，分给哪一目录使用，==它归根结底就只有一个根目录，一个独立且唯一的文件结构== 。
- Linux中每个分区都是用来组成整个文件系统的一部分。
- ==Linux 采用了一种叫“载入”的处理方法，它的整个文件系统中包含了一整套的文件和目录，且将一个分区和一个目录联系起来==。
- 这时要载入的一个分区将使它的存储空间在一个目录下获得。

#### 8.1.2 硬盘说明

1、Linux 硬盘分 IDE 硬盘和 SCSI 硬盘，目前基本上是 SCSI 硬盘。

2、对于 IDE 硬盘，驱动器标识符为`hdx~`,其中`hd`表明分区所在设备的类型，这里是指 IDE 硬盘了。

`x`为盘号(a 为基本盘, b 为基本从属盘, c 为辅助主盘, d 为辅助从属盘）,`~`代表分区，前四个分区用数字 1 到 4 表示，它们是主分区或扩展分区，从 5 开始就是逻辑分区。

3、对于 SCSI 硬盘则标识为`sdx~`，SCSI 硬盘是用`sd`来表示分区所在设备的类型的，其余则和 IDE 硬盘的表示方法一样。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529222917.png)

#### 8.1.3 查看所有设备挂载

常用命令: `lsblk` 或者 `lsblk -f`

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529223558.png)

### 8.2 挂载案例实现

#### 8.2.1 增加硬盘步骤1

在【虚拟机】菜单中，选择【设置】，然后设备列表里添加硬盘，然后一路【下一步】，中间只有选择磁盘大小的地方
需要修改，至到完成。然后重启系统。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529233318.png" style="zoom: 80%;" />

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529233510.png)

执行` lsblk -f`命令！！！

·![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529234137.png)

#### 8.2.2 增加硬盘步骤2

1、执行分区命令 `fdisk /dev/sdb`

- 开始对/sdb 分区。
- m 显示命令列表
- p 显示磁盘分区 同 `fdisk –l`
- n 新增分区
- d 删除分区
- w 写入并退出

2、具体实现

开始分区后输入n，新增分区，然后选择p ，分区类型为主分区。两次回车默认剩余全部空间。最后输入w写入分区并退出，若不保存退出输入q。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210529234950.png" style="zoom:80%;" />

#### 8.2.3 增加硬盘步骤 3

1、挂载: 将一个分区与一个目录联系起来，mount 设备名称 挂载目录

```shell
mount /dev/sdb1 /newdisk
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530001720.png" style="zoom:80%;" />

2、卸载挂载点，umount 设备名称 或者 挂载目录

```shell
mount /dev/sdb1 或者 umount /newdisk
```

3、==用命令行挂载, 重启后会失效==。

#### 8.2.4 增加硬盘步骤 4

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530104140.png" style="zoom:80%;" />

1、永久挂载: 通过修改/etc/fstab 实现挂载。

```shell
vim /etc/fstab
```

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530083954.png)

2、添加完成后 执行 `mount -a`即刻生效！！！

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530084131.png)

### 8.3 磁盘查询

#### 8.3.1 磁盘使用情况

1、基本语法: `df -h`

2、应用实例：查询系统整体磁盘使用情况

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530093403.png)

#### 8.3.2 指定磁盘使用情况

1、查询指定目录的磁盘占用情况，默认为当前目录。

| 基本参数      | 说明                       |
| ------------- | -------------------------- |
| -s            | 指定目录占用大小汇总       |
| -h            | 带计量单位                 |
| -a            | 含文件                     |
| --max-depth=1 | 子目录深度                 |
| -c            | 列出明细的同时，增加汇总值 |

2、案例说明

查询 `/home`目录的磁盘占用情况，深度为 1。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530095408.png" style="zoom:80%;" />

#### 8.3.3 工作实用指令

1、统计/home 文件夹下文件的个数

```shell
ls -l /home | grep "^-" | wc -l
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530095828.png)

2、统计/home 文件夹下目录的个数

```shell
ls -l /home | grep "^d" | wc -l
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530100024.png)

3、统计/home 文件夹下文件的个数，包括子文件夹里的。

```shell
ls -lR /home | grep "^-" | wc -l
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530100221.png)

4、统计/home 文件夹下目录的个数，包括子文件夹里的

```shell
ls -lR /home | grep "^d" | wc -l
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530101506.png)

5、以树状显示目录结构 tree 目录

```shell
yum install tree
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530101754.png" style="zoom: 80%;" />

## 9-Linux网络配置

### 9.1 网络配置原理图

<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530130202.png" style="zoom:80%;" />	

### 9.2 查看网络IP和网关

#### 9.2.1 修改 IP 地址

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530130842.png" style="zoom:80%;" />

#### 9.2.2 查看网关

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530131301.png" style="zoom:80%;" />

#### 9.2.3 查看 windows网络

执行命令：`ipconfig`

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530131626.png" style="zoom:67%;" />

#### 9.2.4 查看linux的网络配置

执行命令：`ifconfig`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530132005.png)

#### 9.2.5 测试主机之间网络连通性

1、基本语法

```shell
ping 目的主机 （功能描述：测试当前服务器是否可以连接目的主机）
```

2、应用实例

主机`ping`服务器！！！

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530132609.png" style="zoom:80%;" />

服务器`ping`主机！！！

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530132722.png)

### 9.3 linux 网络环境配置

#### 9.3.1 自动获取

通过界面的来设置自动获取 ip，特点是：==linux 启动后会自动获取 IP,缺点是每次自动获取的 ip 地址可能不一样==。

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530142411.png)

#### 9.3.2 指定固定ip

1、直接修改配置文件来指定 `IP`,并可以连接到外网。

2、将 `ip` 地址设置为静态，使用指令`vim /etc/sysconfig/network-scripts/ifcfg-ens33`

```shell
TYPE="Ethernet"
PROXY_METHOD="none"
BROWSER_ONLY="no"
BOOTPROTO="static" # 设置为静态
DEFROUTE="yes"
IPV4_FAILURE_FATAL="no"
IPV6INIT="yes"
IPV6_AUTOCONF="yes"
IPV6_DEFROUTE="yes"
IPV6_FAILURE_FATAL="no"
IPV6_ADDR_GEN_MODE="stable-privacy"
NAME="ens33"
UUID="5e2257e9-10e6-47c8-a3c0-66008f54b93c"
DEVICE="ens33"
ONBOOT="yes"
# IP地址
IPADDR=192.168.50.128
# 网关
GATEWAY=192.168.50.2
# 域名解析器
DNS1=192.168.50.2
```

3、修改虚拟网络编辑器

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530151546.png" style="zoom:80%;" />

4、重启网络服务或者重启系统生效，执行命令`service network restart`或者`reboot`。

### 9.4  设置主机名和hosts映射

#### 9.4.1 设置主机名

1、指令 `hostname `： 查看主机名

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530152039.png)

2、修改文件在`/etc/hostname`指定。

```shell
vim /etc/hostname
```

3、修改后， 重启生效。

#### 9.4.2 设置 hosts 映射

1、windows配置

在 `C:\Windows\System32\drivers\etc\hosts`文件指定即可

```shell
192.168.50.128 Linux
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530161631.png" style="zoom:80%;" />

2、linux系统配置

在 `/etc/hosts`文件指定，执行`vim /etc/hosts`

```css
192.168.3.9 GuardWhy
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530162151.png)

### 9.5 主机名解析过程

#### 9.5.1 Hosts 是什么

一个文本文件，用来录记录 `IP` 和 `Hostname`( 主机名)的映射关系。

#### 9.5.2 DNS基本概念

`DNS`，就是 `Domain Name System` 的缩写，翻译过来就是域名系统，是互联网上作为域名和` IP` 地址相互映射的一个分布式数据库。

#### 9.5.3 案例说明

用户在浏览器输入了 [www.imooc.com](www.imooc.com)

具体步骤：

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530164355.png)

1、浏览器先检查浏览器缓存中有没有该域名解析 IP 地址，有就先调用这个 IP 完成解析；如果没有，就检查 DNS 解析器缓存，如果有直接返回 IP 完成解析。这两个缓存，可以理解为本地解析器缓存。

2、一般来说，当电脑第一次成功访问某一网站后，在一定时间内，浏览器或操作系统会缓存他的 IP 地址。

3、如果本地解析器缓存没有找到对应映射，检查系统中 hosts 文件中有没有配置对应的域名 IP 映射，如果有，则完成解析并返回。

4、如果本地DNS解析器缓存和 hosts文件 中均没有找到对应的 IP，则到域名服务 DNS 进行解析域。

## 10-Linux进程管理

### 10.1 基本介绍

在操作系统中，每个执行的程序都称为一个进程。每一个进程都分配一个 ID 号(pid,进程号)。

<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530221838.png" style="zoom:80%;" />	

每个进程都可能以两种方式存在的。前台与后台，所谓前台进程就是用户目前的屏幕上可以进行操作的。后台进程则是实际在操作，但由于屏幕上无法看到的进程，通常使用后台方式执行。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210530221715.png)

一般系统的服务都是以后台进程的方式存在，而且都会常驻在系统中，直到关机才才结束。

### 10.2 系统执行进程

#### 10.2.1 基本介绍

`ps 命令`是用来查看目前系统中，有哪些正在执行，以及它们执行的状况。可以不加任何参数。

| 指令  | 作用                       |
| ----- | -------------------------- |
| ps -a | 显示当前终端的所有进程信息 |
| ps -u | 以用户的格式显示进程信息   |
| ps -x | 显示后台进程运行的参数     |

**ps 详解**

执行指令: `ps -aux | more`

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531093741.png)

`ps命令`显示的信息选项

| 字段    | 说明                                                         |
| ------- | ------------------------------------------------------------ |
| USER    | 进程执行用户                                                 |
| PID     | 进程号                                                       |
| %CPU    | 占用CPU的百分比                                              |
| %MEM    | 进程占用物理内存的百分比                                     |
| VSZ     | 进程占用的虚拟内存大小                                       |
| RSS     | 进程占用的物理内存大小                                       |
| TTY     | 终端                                                         |
| STAT    | 进程状态，其中 S-睡眠，s-表示该进程是会话的先导进程，N-表示进程拥有比普通优先级更低的优先级<br/>R-正在运行，D-短期等待，Z-僵死进程，T-被跟踪或者被停止等. |
| START   | 执行的开始时间                                               |
| TIME    | 占用的CPU时间，CPU 时间，即进程使用 CPU 的总时间。           |
| COMMAND | 进程名，执行该进程的指令，启动进程所用的命令和参数，如果过长会被截断显示。 |

#### 10.2.2 父子进程

1、全格式显示当前所有的进程，查看进程的父进程，查看 sshd 的父进程信息。

```shell
ps -ef|grep sshd
```

`-e`显示所有进程，`-f` 全格式。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531105804.png)

2、查询所有的进程，执行`ps -ef | more`

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531110124.png)

| 字段  | 说明                                                         |
| ----- | ------------------------------------------------------------ |
| UID   | 用户 ID                                                      |
| PID   | 进程 ID                                                      |
| PPID  | 父进程 ID                                                    |
| C     | CPU 用于计算执行优先级的因子。数值越大，表明进程是 CPU 密集型运算，执行优先级会降低<br/>数值越小，表明进程是 I/O 密集型运算，执行优先级会提高。 |
| STIME | 进程启动的时间                                               |
| TTY   | 完整的终端名称                                               |
| TIME  | CPU 时间                                                     |
| CMD   | 启动进程所用的命令和参数。                                   |

3、父子进程图解

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531111931.png)

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531111621.png)

### 10.3 终止进程 

#### 10.3.1 基本概念

若是某个进程执行一半需要停止时，或是已消了很大的系统资源时，此时可以考虑停止该进程。使用`kill 命令`来完成此项任务。

#### 10.3.2 基本语法

- kill [选项] 进程号(功能描述：通过进程号杀死/终止进程)。
- killall 进程名称(功能描述：通过进程名称杀死进程，也支持通配符，这在系统因负载过大而变得很慢时很有用)。
- kill -9 进程号: 表示强迫进程立即停止。

#### 10.3.3 案例说明

1、踢掉某个非法登录用户

```shell
kill  11672 
```

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531111931.png)	

2、 终止远程登录服务 sshd, 在适当时候再次重启 sshd 服务

执行`ps -aux | grep sshd`命令

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531111931.png)

```shell
kill  9809
```

再次重启 sshd 服务,执行命令: `/bin/systemctl start sshd.service`

3、强制杀掉一个终端。

```shell
kill -9 对应的进程号
```

### 10.4 查看进程树 pstree

#### 10.4.1 基本语法

pstree [选项] ,可以更加直观的来看进程信息。

| 常用选项 | 具体说明           |
| -------- | ------------------ |
| -p       | 显示进程的 PID     |
| -u       | 显示进程的所属用户 |

#### 10.4.2 案例说明

1、树状的形式显示进程的 pid

```shell
pstree -p
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531133600.png" style="zoom:80%;" />

2、树状的形式进程的用户

```shell
pstree -u
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531133825.png" style="zoom:80%;" />

### 10.5 服务管理

#### 10.5.1 基本介绍

服务(service) 本质就是进程，但是是运行在后台的，通常都会监听某个端口，等待其它程序的请求，比如(mysqld , sshd
防火墙等)，因此我们又称为守护进程，是 Linux 中非常重要的知识点。

#### 10.5.2 service 管理指令

1、CentOS7.0 后很多服务不再使用`service` ,而是 `systemctl `，service 指令管理的服务在 `/etc/init.d `查看(CentOS 7.x以后)

```shell
ls -l /etc/init.d/
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531172740.png)

2、案例说明

使用 service 指令，查看，关闭，启动 network，注意: 在虚拟系统演示，因为网络连接会关闭。

```shell
service network status
service network stop
service network start
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531182319.png)

#### 10.5.3 查看服务名

1、使用 `setup` -> 系统服务 就可以看到全部

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531182819.png" style="zoom:80%;" />

2、通过`/etc/init.d` 看到 service 指令管理的服务。

```shell
ls -l /etc/init.d/
```

#### 10.5.4 systemctl 管理指令

1、基本语法

```shell
systemctl [start | stop | restart | status] 服务名
```

2、systemctl 指令管理的服务在 /usr/lib/systemd/system 查看

```shell
ls -l /usr/lib/systemd/system
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531185751.png)

#### 10.5.5 设置服务启动状态

1、基本语法

- `systemctl list-unit-files [ | grep 服务名]`： 查看服务开机启动状态，grep可以进行过滤。
- `systemctl enable 服务名 `：设置服务开机启动。
- `systemctl disable 服务名`  : 关闭服务开机启动。
- `systemctl is-enabled 服务名` : 查询某个服务是否是自启动的。

2、防火墙配置

| **命令**                                                     | **作用**             |
| ------------------------------------------------------------ | -------------------- |
| **systemctl start  firewalld**                               | 开启防火墙           |
| **systemctl stop   firewalld**                               | 关闭防火墙           |
| **systemctl   enable firewalld**                             | 开启自启动防火墙     |
| **systemctl   disable firewalld**                            | 关闭开机自启动防火墙 |
| **systemctl  status firewalld**                              | 显示防火墙状态       |
| **firewall-cmd --zone=public --add-port=9000/tcp --permanent** | 开启防火墙端口       |
| **systemctl restart firewalld**                              | 重启防火墙           |

3、查看防火墙的状态

```css
systemctl status firewalld
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531212408.jpg)

4、开启防火墙

```css
systemctl start firewalld
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531212503.jpg)

5、开启端口

```css
firewall-cmd --zone=public --add-port=3306/tcp --permanent--zone #作用域--add-port=3306/tcp  #添加端口，格式为：端口/通讯协议
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531212620.jpg)

​    重新载入,才能生效: `firewall-cmd --reload`命令

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531193043.png)

7、关闭端口：`firewall-cmd --permanent --remove-port=端口号/协议`

```shell
firewall-cmd --permanent --remove-port=3306/tcp
```

重新载入,才能生效: `firewall-cmd --reload`命令

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531194324.png)

8、查看防火墙规则

```css
firewall-cmd --list-all   # 查看全部信息firewall-cmd --list-ports  # 只看端口信息
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531212711.jpg)

### 10.6 动态监控进程

#### 10.6.1 基本介绍

top 与 ps 命令很相似。它们都用来显示正在执行的进程。Top 与 ps 最大的不同之处，在于 top 在执行一段时间可以更新正在运行的的进程。

1、基本语法

| top[选项] | 功能                                       |
| --------- | ------------------------------------------ |
| -d 秒数   | 指定top命令每隔几秒更新，默认是3秒         |
| - i       | 使top不显示任何闲置或者僵死进程            |
| - p       | 通过指定监控进程ID来仅仅监控某个进程的状态 |

执行`top`指令

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531195433.png)

2、参数分析:

| 参数         | 具体说明      |
| ------------ | ------------- |
| 19:53:47 up  | 当前时间      |
| 9:38         | 系统运行时间  |
| users        | 用户数量      |
| load average | 负载均衡      |
| Tasks        | 系统的任务数  |
| zombie       | 将死进程      |
| us           | 用户占用的cpu |
| sy           | 系统占用的cpu |
| id           | 空闲cpu       |
| Mem          | 内存占用情况  |

3、交互操作

执行`top`指令

| 基本操作 | 功能                            |
| -------- | ------------------------------- |
| P        | 以CPU使用率排序，默认就是此项。 |
| M        | 以内存的使用率排序              |
| N        | 以PID排序                       |
| q        | 退出top                         |

#### 10.6.2 案例说明

1、监视特定用户, 比如监控`guardwhy`用户

- 输入`top`指令，按`Enter`键，查看执行的进程，然后输入`u`回车，再输入用户名(`guardwhy`)。


2、终止指定的进程, 比如要结束`guardwhy`登录

- 输入`top`指令，按`Enter`键，查看执行的进程，然后输入`k`回车，再输入要结束的进程 ID 号。


3、指定系统状态更新的时间(每隔 10 秒自动更新), 默认是 3 秒。

```shell
top -d 10
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531211938.png)

### 10.7 监控网络状态

#### 10.7.1 基本语法

| netstat [选项] | 功能                         |
| -------------- | ---------------------------- |
| **无参**       | 查看活动的网络进程           |
| -n             | 显示进程访问的IP地址和端口号 |
| -t             | 显示使用TCP协议的进程        |
| -l             | 显示正确监听中进程           |
| -p             | 显示进程的程序的名字         |
| - an           | 按一定顺序排列输出           |

#### 10.7.2 案例说明

1、查看服务名为` sshd `的服务的信息。

```shell
netstat -anp | grep sshd
```

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531214315.png)

2、查看网络的进程

```shell
netstat
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531220635.jpg)

3、显示TCP协议和监听中的网络连接

```shell
netstat -tnetstat -tl
```

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531221047.png)

4、显示监听的端口号和程序的名字

```shell
netstat -tln
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531222324.jpg)

```shell
netstat -tlnp
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210531222528.jpg)

##  11-Linux软件安装

### 11.1 rpm 包的管理

#### 11.1.1 基本介绍

rpm 用于互联网下载包的打包及安装工具，它包含在某些 Linux 分发版中。它生成具有.RPM 扩展名的文件。RPM是 RedHat Package Manager（RedHat 软件包管理工具）的缩写，类似 windows 的 setup.exe，这一文件格式名称虽然打上了 RedHat 的标志，但理念是通用的。

Linux 的分发版本都有采用（suse,redhat, centos 等等），可以算是公认的行业标准了。
rpm 包类似于`windows`的360管家

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601200401.png)

#### 11.1.2 语法格式

| **rpm 参数 软件包** | **参数说明**                         |
| ------------------- | ------------------------------------ |
| **作用**            | 类似于一个软件管理工具               |
| **-v**              | 显示软件安装详情                     |
| **-q <软件名>**     | 查询指定的软件是否安装了             |
| **-a**              | 查询所有已经安装的软件               |
| **-h**              | 显示软件安装的进度条，安装的百分比   |
| **-i <软件名>**     | 安装 `install`，指定要安装的软件名字 |

> **常用的组合**

1、查询所安装的所有 rpm 软件包

```shell
rpm -qa | more
```

2、查询软件包是否安装

```shell
rpm -q 软件包名
```

3、查询软件包信息

```shell
rpm -qi 软件包名
```

4、卸载软件

```shell
rpm -e RPM 包的名称
```

5、查看所有安装的软件

```
rpm -qa
```

6、安装指定的软件

```
rpm -ivh 软件名
```

### 11.2 yum

#### 11.2.1 基本介绍

Yum 是一个 Shell 前端软件包管理器。基于 RPM 包管理，能够从指定的服务器自动
下载 RPM 包并且安装，可以自动处理依赖性关系，并且一次安装所有依赖的软件包。

#### 11.2.2 yum 的基本指令

1、查询 yum 服务器是否有需要安装的软件

```shell
yum list|grep xx 软件列表
```

2、安装指定的 yum 包

```shell
yum -y install 软件名
```

3、卸载软件

```shell
yum -y remove 软件名
```

### 11.3 安装 JDK

#### 11.3.1 安装步骤

1、`mkdir /opt/jdk`文件夹

2、通过 xftp6 上传到 `/opt/jdk` 下

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601134330.png)

3、`cd /opt/jdk`，解压 `tar -zxvf jdk-8u261-linux-x64.tar.gz`。

4、创建`mkdir /usr/local/java`文件夹。

5、`mv /opt/jdk/jdk1.8.0_261 /usr/local/java`，配置环境变量的配置文件` vim /etc/profile`。

```shell
vim /etc/profile
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601134600.png)

```shell
export JAVA_HOME=/usr/local/java/jdk1.8.0_261export PATH=$JAVA_HOME/bin:$PATH
```

6、最后执行命令`source /etc/profile`，重启系统，让新的环境变量生效。

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601135005.png)	

### 11.4 tomcat 的安装

#### 11.4.1 安装步骤

1、上传安装文件，并解压缩到`/opt/tomcat`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601135314.png)

2、创建`mkdir /usr/local/tomact`文件夹。

3、`mv /opt/tomact/apache-tomcat-8.5.59 /usr/local/tomact/`，配置环境变量的配置文件` vim /etc/profile`。

```shell
export CATALINA_HOME=/usr/local/tomact/apache-tomcat-8.5.59export PATH=$CATALINA_HOME/bin:$PATHsource /etc/profile
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601154154.png)	

4、开放防火墙端口

```shell
firewall-cmd --zone=public --add-port=8080/tcp --permanentfirewall-cmd --reload
```

5、查询端口是否开启

```shell
firewall-cmd --query-port=8080/tcp
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601155011.png)

6、执行`startup.sh`，启动Tomact，打开浏览器

<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601155350.png" style="zoom:80%;" />

7、执行`shutdown.sh`，关闭Tomact！！！

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601155613.png)

### 11.5 安装MySQL5.7 

#### 11.5.1 安装步骤

1、创建mysql文件夹。

```shell
mkdir usr/local/mysql
```

2、下载Mysql的repo源

```shell
wget http://dev.mysql.com/get/mysql57-community-release-el7-8.noarch.rpm
```

3、安装rpm包

```shell
rpm -ivh mysql57-community-release-el7-8.noarch.rpm
```

4、安装Mysql

```shell
yum install mysql-server
```

5、启动服务

```shell
service mysqld start
```

6、查看服务状态

```shell
systemctl status mysqld
```

7、使用root用户登录

```shell
mysql -u root
```

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601190034.png)	

找到临时密码，执行指令`grep password /var/log/mysqld.log`

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601190520.png)

8、修改临时密码

```shell
alter user 'root'@'localhost' identified by 'Guardwhy@666';
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601190844.png" style="zoom:80%;" />

#### 11.5.2 图形化界面访问数据库

1、启动图形化界面工具`Navicat`连接虚拟机中Mysql数据库，点击链接数据库报错，出现错误号码`1130`。

2、使用root权限登录数据库后选择mysql库。

```shell
mysql -u root -puse mysql;
```

3、查看mysql库中的user表的host值

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601194107.png)

4、将host值修改为`通配符%`

```shell
update user set host='%' where user='root';flush privileges;
```

5、查看修改结果并重新测试。

```shell
select user,host from user;
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601195422.png)

6、开启`3306`端口

```shell
firewall-cmd --zone=public --add-port=3306/tcp --permanentfirewall-cmd --reloadfirewall-cmd --query-port=3306/tcp
```

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601195630.png)

7、Navicat远程连接数据库，出现`11001`。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601195820.png" style="zoom:80%;" />

原因很简单，==查看ip/域名前面有没有空格==，去除空格，连接成功！！！！

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601200033.png" style="zoom:80%;" />

## 12-Linux shell编程

### 12.1 Shell定义

1、基本定义

Shell 是==一个命令行解释器==，它为用户提供了一个向 Linux 内核发送请求以便运行程序的界面系统级程序，用户可以用 Shell 来启动、挂起、停止甚至是编写一些程序。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601212205.png" style="zoom:80%;" />

2、==CentOS 7 默认使用的 Shell 是 bash==。

3、bash基本特点

- 一条命令只做一件事
- 为了组合命令和多次执行，使用脚本文件来保存需要执行的命令。
- 赋予该文件执行权限（chmod u+rx filename）

### 12.2 Shell执行方式

#### 12.2.1 脚本格式要求

- 脚本以`#!/bin/bash` 开头。
- 脚本需要有可执行权限。

#### 12.2.2 基本语法

1、创建shell脚本

```shell
vim *.sh
```

2、编写内容，脚本以`#!/bin/bash`开头。

```shell
#!/bin/bash
echo "具体内容....."
```

3、给脚本文件赋予可执行权限

```shell
chmod u+rx filename 
```

4、执行脚本命令

- bash ./filename.sh(外部命令)
- ./filename.sh(外部命令)
- source ./filename.sh(内建命令)
- .filname.sh(内建命令)

注意: 内建命令和外部命令的区别: 内建命令不需要创建子进程，内建命令对当前 Shell 生效。

#### 12.2.3 案例说明

1、创建一个 Shell 脚本，输出 hello world!，先执行`vim myShell.sh`

```shell
#!/bin/bash
echo "hello,world~"
```

2、添加权限`chmod u+rx myShell.sh`

3、执行脚本语言`./myShell.sh`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601220004.jpg)

### 12.3 Shell的变量

#### 12.3.1 变量介绍

1、linux Shell 中的变量分为，==系统变量和用户自定义变量==。

2、系统变量：`$HOME、$PWD、$SHELL、$USER` 等等，比如： `echo $HOME `

 ```css
#!/bin/bash
echo "PATH=$PATH" #输出系统变量
echo "user=$USER"
 ```

3、显示当前shell中所有的变量: ==set==

#### 12.3.2 shell变量的定义

1、基本语法

定义变量： 变量=值。

撤销变量: unset 变量。

声明静态变量：readonly 变量，注意：不能 unset

2、入门案例1

定义变量a，撤销变量a。

```shell
#!/bin/bash"
a=100
echo "a=$a"
unset a
echo "a=$a"
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601222548.jpg)

3、入门案例2

声明静态变量a=98，==不能unset==

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601222744.jpg)

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601222824.jpg)

4、定义变量的规则

- 变量名称可以由字母、数字和下划线组成，但是不能以数字开头。
- 等号两侧不能有空格。
- 变量名称一般习惯为大写。

5、将命令的返回值赋给变量

```shell
A=`ls -la` 反引号，运行里面的命令，并把结果返回给变量 A
A=$(ls -la) 等价于反引号
```

**代码示例**：

```shell
#!/bin/bash
RESULT='ls -l /home'
echo $RESULT   #使用''将命令括起来
echo ""

MY_DATE=$(date)
echo "date=$MY_DATE"  #使用$()来执行也可以
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601225315.jpg)

### 12.4 设置环境变量

#### 12.4.1 基本语法

| 参数                 | 功能描述                             |
| -------------------- | ------------------------------------ |
| export 变量名=变量值 | 将 shell 变量输出为环境变量/全局变量 |
| source 配置文件      | 让修改后的配置信息立即生效           |
| echo $变量名         | 查询环境变量的值                     |

#### 12.4.2 入门案例

1、在etc/profile 文件中定义 TOMCAT_HOME 环境变量。

```css
vim /etc/profile
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210601235804.jpg)

**注意**：在输出 `TOMCAT_HOME` 环境变量前，要先执行`source /etc/profile`，这样才能真正的生效。

2、查看环境变量 TOMCAT_HOME 的值。

```css
echo $TOMCAT_HOME
```

3、在另一个shell中执行环境变量

shell 脚本的多行注释
`:<<! 内容 !`

```css
#!/bin/bash#多行注释:<<!    RESULT='ls -l /home'    echo $RESULT    echo ""    MY_DATE=$(date)    echo "date=$MY_DATE"!#使用环境变量echo "tomcathome=$TOMCAT_HOME"
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602000150.jpg)

### 12.5 位置参数变量

#### 12.5.1 基本介绍

当执行一个 shell 脚本时，如果希望获取到命令行的参数信息，就可以使用到位置参数变量。
比如 ：`./myshell.sh 10 15` , 这个就是一个执行 shell 的命令行，可以在 myshell 脚本中获取到参数信息。

####  12.5.2 基本语法

| 参数 | 功能描述                                                     |
| ---- | ------------------------------------------------------------ |
| `$n` | `n `为数字，`$0 `代表命令本身，`$1-$9 `代表第一到第九个参数，十以上的参数，十以上的参数需要用大括号包含，如`${10}`。 |
| `$*` | 这个变量代表命令行中所有的参数，`$*`把所有的参数看成一个整体。 |
| `$@` | 这个变量也代表命令行中所有的参数，不过`$@`把每个参数区分对待。 |
| `$#` | 这个变量代表命令行中所有参数的个数。                         |

#### 12.5.3 入门案例

编写一个 shell 脚本 `positionPara.sh` ，在脚本中获取到命令行的各个参数信息。

```css
#!/bin/bash#获取到各个参数echo "$0 $1 $2"echo "$*"echo "$@"echo "参数个数=$#"
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602001508.jpg)

### 12.6 预定义变量

#### 12.6.1 基本概念

shell 设计者事先已经定义好的变量，可以直接在 shell 脚本中使用

#### 12.6.2 基本语法

| 参数 | 功能描述                                                     |
| ---- | ------------------------------------------------------------ |
| $$   | 当前进程的进程号（PID）                                      |
| $!   | 后台运行的最后一个进程的进程号（PID）                        |
| $？  | 最后一次执行的命令的返回状态。如果这个变量的值为 0，证明上一个命令正确执行。<br/>如果这个变量的值为非 0（具体是哪个数，由命令自己来决定），则证明上一个命令。 |

#### 12.6.3 案例说明

在一个 shell 脚本中简单使用一下预定义变量

```shell
#!/bin/bashecho "当前的进程号=$$"#后台的方式运行myShell.sh./myShell.sh &echo "最后的进程的号=$!"echo "执行的值=$?"
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602002346.jpg)

###  12.7 运算符

#### 12.7.1 基本概念

在 shell 中进行各种运算操作。

#### 12.7.2 基本语法

1、`$((运算式))`或`$[运算式]`
2、expr m + n，注意 expr 运算符间要有空格。如果希望将 expr 的结果赋给某个变量，使用 ``！！
3、expr m - n。
4、`expr \*, /, %` 乘，除，取余。

#### 12.7.3 案例说明

1、计算（2+3）* 4 的值

2、求出命令行的两个参数[整数]的和

```css
#!/bin/bash#方式一RESULT1=$(((2+3)*4))echo "resultt1=$RESULT1"#方式2RESULT2=$[(2+3)*4]echo "result2=$RESULT2"#方式三TEMP=`expr 2 + 3`RESULT3=`expr $TEMP \* 4`echo "result3=$RESULT3"#求两个数之和SUM=$[$1+$2]echo "SUM=$SUM"
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602003016.jpg)

### 12.8  判断语句

#### 12.8.1 基本语法

```shell
[condition] (注意condition前后要有空格)# 非空返回true，可使用$?验证(0为true, >1为false) 
```

#### 12.8.2 常用判断条件

1、两个整数的比较(= 字符串比较)

```shell
-lt 小于-le 小于等于  little equal-eq 等于-gt 大于-ge 大于等于-ne 不等于
```

2、按照文件权限进行判断

```shell
-r 有读的权限-w 有写的权限-x 有执行的权限
```

3、按照文件类型进行判断

```shell
-f 文件存在并且是一个常规的文件-e 文件存在-d 文件存在并是一个目录
```

#### 12.8.3 案例说明

```css
#!/bin/bash#案例1:"ok"是否等价于"ok"if [ "ok" = "ok" ]then     echo "equal"fi#案例2:23是否大于等于22if [ 23 -gt 22 ]then     echo "大于"fi#案例3 /home/shell/kobe.java文件是否存在if [ -e /home/shell/kobe.java ]then     echo "存在"fi
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602004143.jpg)

### 12.9 流程控制

#### 12.9.1 if 判断基本语法

注意事项：[ 条件判断式 ]，中括号和条件判断式之间必须有空格。

```shell
if condition1then    command1elif condition2 then     command2else    commandNfi
```

#### 12.9.2 案例说明

写一个 shell 程序，如果输入的参数，大于等于 60，则输出及格了，如果小于 60,则输出不及格。

```shell
#!/bin/bashif [ $1 -ge 60 ]then     echo "及格了"elif [ $1 -lt 60 ]then     echo "不及格"fi
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602004724.jpg)

#### 12.9.3 case基本语法

```shell
case $变量名 in"值 1"）如果变量的值等于值 1，则执行程序 1;;"值 2"）如果变量的值等于值 2，则执行程序 2;;…省略其他分支…*）如果变量的值都不是以上的值，则执行此程序;;esac
```

#### 12.9.4 案例说明

当命令行参数是  1 时，输出  "周一",  是 2 时，就输出"周二",其它情况输出   "other"。

```shell
#!/bin/bashcase $1 in"1")echo "周一";;"2")echo "周二";;*)echo "other";;esac
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602005218.jpg)

#### 12.9.5 for循环语法1

```css
for 变量 in 值 1 值 2 值 3…do	程序/代码done
```

#### 12.9.6 案例说明1

打印命令行输入的参数 [这里可以看出`$*` 和 `$@` 的区别]

```css
#!/bin/bash#打印命令行输入的参数# 使用$*for i in "$*"do    echo "the num is $i"doneecho "=========="#使用$@for j in "$@"do    echo "the num is $j"done
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602005528.jpg)

#### 12.9.7 for循环语法2

```css
for (( 初始值;循环控制条件;变量变化 ))    do     程序    done
```

#### 12.9.8 案例说明2

从 1 加到 100 的值输出显示

```shell
#!/bin/bash#定义一个变量SUM=0for((i=1;i<=100;i++))do    SUM=$[$SUM+$i]doneecho "sum=$SUM"
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602005727.jpg)

#### 12.9.9 while循环语法

while 和 [有空格，条件判断式和 [也有空格

```css
while [ 条件判断式 ] do  程序 done
```

#### 12.9.10 案例说明

从命令行输入一个数 n，统计从 1+..+ n 的值是多少？

```shell
#!/bin/bashSUM=0i=0while [ $i -le $1 ]do      SUM=$[$SUM+$i]      #i 自增      i=$[$i+1]doneecho "sum=$SUM"
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602010055.jpg)

### 12.10 read控制台输入

#### 12.10.1 基本语法

变量：指定读取值的变量名

| read(选项)(参数) | 功能描述                                                     |
| ---------------- | ------------------------------------------------------------ |
| -p               | 指定读取值时的提示符                                         |
| -t               | 指定读取值时等待的时间（秒），如果没有在指定的时间内输入，就不再等待了。 |

#### 12.10.2 案例说明

- 读取控制台输入一个 num 值。
- 读取控制台输入一个 num 值，在 10 秒内输入。

```css
#!/bin/bash#读取控制台输入一个num值read -p "请输入一个数num1=" NUM1echo "你输入的值是num1=$NUM1"read -t 10 -p "请输入一个数num2=" NUM2echo "你输入的值是num2=$NUM2"
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602010710.jpg)

### 12.11 函数

#### 12.11.1 函数介绍

shell 编程和其它编程语言一样，有系统函数，也可以自定义函数。

#### 12.11.2 系统函数

1、basename function：返回完整路径最后 / 的部分，常用于获取文件名。

2、案例说明1

返回`/home/curry/test.java`中的test.java部分。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602011207.jpg)

3、dirname function：返回完整路径最后 / 的前面的部分，常用于返回路径部分

4、案例说明2

返回`/home/aaa/test.txt`的/home/aaa

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602011353.jpg)

#### 12.11.3 自定义函数

1、基本语法

```css
[ function ] funname[()]{	Action;    [return int;]}调用直接写函数名：funname [值]
```

2、案例说明

计算输入两个参数的和(read) , getSum

```shell
#!/bin/bashfunction getSum(){    SUM=$[$n1+$n2]    echo "和是=$SUM"}read -p "请输入第一个数n1:" n1read -p "请输入第一个数n2:" n2#调用getSumgetSum $n1 $n2
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602011524.jpg)

### 12.12 综合案例

#### 12.12.1 需求分析

1、每天凌晨 2:30 备份 数据库 `db_mybatis 到 /data/backup/db`。
2、备份开始和备份结束能够给出相应的提示信息。
3、备份后的文件要求以备份时间为文件名，并打包成 `.tar.gz` 的形式，比如：2021-03-12_230201.tar.gz。
4、在备份的同时，检查是否有 10 天前备份的数据库文件，如果有就将其删除。

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602112618.png)

#### 12.2.2 案例实现

1、数据表SQL

```sql
-- 创建jdbc_user表CREATE TABLE jdbc_user (	id INT PRIMARY KEY AUTO_INCREMENT ,	username VARCHAR(50),	PASSWORD VARCHAR(50),	birthday DATE);-- 添加数据insert into jdbc_user (username, PASSWORD, birthday) values('Curry', '123', '2001/1/02'),('Kobe', '456', '1991/10/14'),('James', '6666', '1987/11/24'),('Hardon', '6666', '1987/3/24');select * from jdbc_user;
```

2、进入`usr\bin`中创建`mysql_db.backup.sh`脚本

```shell
vim mysql_db_backup.sh # 创建脚本chmod u+x mysql_db_backup.sh # 赋予权限
```

3、继续修改`mysql_db.backup.sh`脚本

```shell
#备份目录BACKUP=/data/backup/db#当前时间DATETIME=$(date +%Y-%m-%d_%H%M%S)echo $DATETIME#数据库的地址HOST=localhost#数据库用户名DB_USER=root#数据库密码DB_PW=Guardwhy@666#备份的数据库名DATABASE=db_mybatis#创建备份目录, 如果不存在，就创建[ ! -d "${BACKUP}/${DATETIME}" ] && mkdir -p "${BACKUP}/${DATETIME}"#备份数据库mysqldump -u${DB_USER} -p${DB_PW} --host=${HOST} -q -R --databases ${DATABASE} | gzip >${BACKUP}/${DATETIME}/$DATETIME.sql.gz#将文件处理成 tar.gzcd ${BACKUP}tar -zcvf $DATETIME.tar.gz ${DATETIME}#删除对应的备份目录rm -rf ${BACKUP}/${DATETIME}#删除 10 天前的备份文件find ${BACKUP} -atime +10 -name "*.tar.gz" -exec rm -rf {} \;echo "备份数据库${DATABASE} 成功~"
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602113827.png)

4、设置定时器，执行`crontab -e`命令，编写以下语句

```shell
30 2 * * * /usr/sbin/mysql_db_backup.sh
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602114625.png)

## 13-Linux日志管理

### 13.1 基本介绍

1、日志文件是重要的系统信息文件，其中记录了许多重要的系统事件，包括用户的登录信息、系统的启动信息、系统的安全信息、邮件相关信息、各种服务相关信息等。

2、日志对于安全来说也很重要，它记录了系统每天发生的各种事情，通过日志来检查错误发生的原因，或者受到攻击时攻击者留下的痕迹。 

3、日志是用来记录重大事件的工具。

### 13.2 系统常用的日志

#### 13.2.1 查看系统日志

1、系统日志文件的保存位置：`/var/log`

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210602235256.png)

2、系统常用的日志

| 日志文件            | 具体作用                                                     |
| ------------------- | ------------------------------------------------------------ |
| `/var/log/boot.log` | 系统启动日志                                                 |
| `/var/log/cron`     | 记录与系统定时任务相关的日志                                 |
| `/var/log/cups/`    | 记录打印信息的日志                                           |
| `/var/log/dmesg`    | 记录系统在开机时内核自检的信总，也可以使用dmesg命令直接查看内核自检信息 |
| `/var/log/btmp`     | 记录错误登录的日志，这个文件是二进制，不能直接用`vi`查看，而要使用`lastb`命名查看。命令如下<br/>`[root@localhost log]#lastb` |
| `/var/log/lasllog`  | 记录系统中所有用户最后一次的登录时间的日志，这个文件也是二进制文件，要使用`lastlog`命令查看。 |
| `/var/Iog/mailog`   | 记录邮件信息的日志。                                         |
| `/var/log/message`  | 记录系统重要消息的日志，这个日志文件中会记录Linux系统的绝大多数重要信息，如果系统出现问题，首先要检查的应该就是这个日志文件。 |
| `/var/log/secure`   | 记录验证和授权方面的信息，只要涉及账户和密码的程序都会记录，比如系统的登录、ssh的登录、su切换用户、sudo授权。甚至添加用户和修改用户密码都会记录在这个日志文件中。 |
| `/var/log/wtmp`     | 永久记录所有用户的登录，注销信息，同时记录系统的后动、重启、关机事件。是二进制文件，而要使用`last`命令查看。 |
| `/var/tun/ulmp`     | 记录当前已经登录的用户信息，这个文件会随着用户的登录和注销而不断变化，只记录当前登录用户的信息，这个文件不能用`vi`查看，而要使用`w、who、user`等命令查看。 |

#### 13.2.2 案例实现

使用` root` 用户通过 `xshell`登陆, 第`1、2`次使用错误的密码，第`3`次使用正确的密码登录成功。

1、先进入log日志目录`cd /var/log`，清空以前日志。。。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603094113.png)

2、查看日志文件/var/log/secure 里有没有记录相关信息。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603094407.png" style="zoom:80%;" />

### 13.3 日志管理服务 rsyslogd

#### 13.3.1 原理示意图

CentOS7.x日志服务是 `rsyslogd` ， CentOS6.x 日志服务是 `syslogd` 。`rsyslogd` 功能更强大，`rsyslogd` 的使用、日志文件的格式，和 `syslogd` 服务兼容的。

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603104255.png)

#### 13.3.2 rsyslogd 相关概念

1、查询 Linux 中的 rsyslogd 服务是否启动。

```shell
ps aux | grep "rsyslog" | grep -v "grep" # grep -v 反向匹配
```

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603105300.png)	

2、查询 rsyslogd 服务的自启动状态

```shell
systemctl list-unit-files | grep rsyslog
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603113128.png)

3、查看配置文件

```shell
more /etc/rsyslog.conf
```

编辑文件时的格式为： `*.* `存放日志文件，其中第一个*代表日志类型，第二个*代表日志级别。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603115459.png" style="zoom:80%;" />

#### 13.3.3 日志类型

| 参数                 | 具体作用                             |
| -------------------- | ------------------------------------ |
| auth                 | pam 产生的日志                       |
| authpriv             | ssh、ftp 等登录信息的验证信息        |
| corn                 | 时间任务相关                         |
| kern                 | 内核                                 |
| lpr                  | 打印                                 |
| mail                 | 邮件                                 |
| mark(syslog)-rsyslog | 服务内部的信息，时间标识             |
| news                 | 新闻组                               |
| uucp                 | unix to nuix copy 主机之间相关的通信 |
| local 1-7            | 自定义的日志设备                     |

#### 13.3.4 日志级别

1、注意：从上到下，级别从低到高，记录信息越来越少。

| 参数    | 具体作用                                             |
| ------- | ---------------------------------------------------- |
| debug   | 有调试信息的，日志通信最多。                         |
| info    | 一般信息日志，最常用。                               |
| notice  | 最具有重要性的普通条件的信息。                       |
| warning | 警告级别                                             |
| err     | 错误级别，阻止某个功能或者模块不能正常工作的信息     |
| crit    | 严重级别，阻止整个系统或者整个软件不能正常工作的信息 |
| alert   | 需要立刻修改的信息                                   |
| emerg   | 内核崩溃等重要信息                                   |
| none    | 什么都不记录                                         |

2、**重点**：由日志服务 rsyslogd 记录的日志文件，日志文件的格式如下：

- 事件产生的时间。
- 产生事件的服务器的主机名。
- 产生事件的服务名或程序名。
- 事件的具体信息。

#### 13.3.5 日志查看实例

执行`more /var/log/secure`命令，这个日志中记录的是用户验证和授权方面的信息。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603134530.png" style="zoom:80%;" />

#### 13.3.6 案例说明

在`/etc/rsyslog.conf` 中添加一个日志文件`/var/log/guardwhy.log`文件,当有事件发送时(比如 sshd 服务相关事件)，该文件会接收到
信息并保存。

1、编写文件

```shell
vim /etc/rsyslog.conf
```

2、自定义日志

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603170537.png)

3、保存文件，重启系统

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603170655.png)

4、查看记录

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603174534.png" style="zoom:80%;" />

### 13.4 日志轮替

#### 13.4.1 基本介绍

1、日志轮替就是把旧的日志文件移动并改名，同时建立新的空日志文件，当旧日志文件超出保存的范围之后，就会进行删除。

#### 13.4.2 日志轮替文件命名

1、centos7 使用 logrotate 进行日志轮替管理，要想改变日志轮替文件名字，通过 /etc/logrotate.conf 配置文件中`dateext`参数。

2、如果配置文件中有`dateext`参数，那么日志会用日期来作为日志文件的后缀，例如 `secure-20201010`。这样日志文件名不会重叠，也就不需要日志文件的改名， 只需要指定保存日志个数，删除多余的日志文件即可。

3、如果配置文件中没有`dateext`参数，日志文件就需要进行改名了。当第一次进行日志轮替时，当前的`secure`日志会自动改名为`secure.1`，然后建`secure`日志， 用来保存新的日志。当第二次进行日志轮替时，`secure.1`会自动改名为`secure.2`， 当前的`secure`日志会自动改名为`secure.1`，然后也会新建`secure`日志，用来保存新的日志，以此类推。

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603180130.png)

4、查看boot.log日志轮替

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603181221.png" style="zoom:80%;" />

#### 13.4.3 logrotate 配置文件

`logrotate.conf` 是全局配置文件，执行命令`cat /etc/logrotate.conf `查看具体信息。

```shell
# see "man logrotate" for details
# rotate log files weekly //每周对日志文件进行一次轮替
weekly

# keep 4 weeks worth of backlogs // 共保存 4 份日志文件，当建立新的日志文件时，旧的将会被删除
rotate 4

# create new (empty) log files after rotating old ones // 创建新的空的日志文件，在日志轮替后
create

# use date as a suffix of the rotated file // 使用日期作为日志轮替文件的后缀
dateext

# uncomment this if you want your log files compressed //日志文件是否压缩。如果取消注释，则日志会在转储的同时进行压缩
#compress

# RPM packages drop log rotation information into this directory
include /etc/logrotate.d

# 包含 /etc/logrotate.d/ 目录中所有的子配置文件。也就 是说会把这个目录中所有子配置文件读取进来，
#下面是单独设置，优先级更高。
# no packages own wtmp and btmp -- we'll rotate them here
/var/log/wtmp {
    monthly # 每月对日志文件进行一次轮替
    create 0664 root utmp # 建立的新日志文件,权限是0664,所有者是root,所属组是utmp组
	minsize 1M # 日志文件最小轮替大小是1MB,也就是日志一定要超过 1MB 才会轮替，否则就算时间达到一个月，也不进行日志转储。
    rotate 1 # 仅保留一个日志备份。也就是只有 wtmp 和 wtmp.1 日志保留而已。
}

/var/log/btmp {
    missingok # 如果日志不存在，则忽略该日志的警告信息。
    monthly
    create 0600 root utmp
    rotate 1
}

# system-specific logs may be also be configured here.
```

| 参 数                   | 参数说明                                                     |
| ----------------------- | ------------------------------------------------------------ |
| daily                   | 日志的轮替周期是每天                                         |
| weekly                  | 日志的轮替周期是每周                                         |
| monthly                 | 日志的轮替周期是每月                                         |
| rotate 数字             | 保留的日志文件的个数。0 指没有备份                           |
| compress                | 日志轮替时，旧的日志进行压缩                                 |
| create mode owner group | 建立新日志，同时指定新日志的权限与所有者和所属组。           |
| mail address            | 当日志轮替时，输出内容通过邮件发送到指定的邮件地址。         |
| missingok               | 如果日志不存在，则忽略该日志的警告信息。                     |
| notifempty              | 如果日志为空文件，则不进行日志轮替。                         |
| minsize 大小            | 日志轮替的最小值。也就是日志一定要达到这个最小值才会轮替，否则就算时间达到也不轮替。 |
| size 大小               | 日志只有大于指定大小才进行日志轮替，而不是按照时间轮替。     |
| dateext                 | 使用日期作为日志轮替文件的后缀。                             |
| sharedscripts           | 在此关键字之后的脚本只执行一次。                             |
| prerotate/endscript     | 在日志轮替之前执行脚本命令。                                 |
| postrotate/endscript    | 在日志轮替之后执行脚本命令。                                 |

#### 13.4.4 自定义日志加入日志轮替

1、方式一：

在`/etc/logrotate.conf `配置文件中写入该日志的轮替策略。

2、方式二：

在`/etc/logrotate.d/`目录中新建立该日志的轮替文件，在该轮替文件中写入正确的轮替策略，因为该目录中的文件都会被`include`到主配置文件中，所以也可以把日志加入轮替。==推荐使用第二种方法，因为系统中需要轮替的日志非常多，如果全都直接写 入==`/etc/logrotate.conf` ==配置文件，那么这个文件的可管理性就会非常差，不利于此文件的维护==。

3、执行命令`cd /etc/logrotate.d/`，查看全部轮替文件。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603215655.png)

#### 13.4.5 案例说明

直接在 `/etc/logrotate.d/` 下创建文件 guardwhylog，执行命令`vim guardwhylog`，具体轮替的效果 可以参考` /var/log` 下的 `boot.log`。

```shell
/var/log/guardwhy.log
{
  missingok
  daily
  copytruncate
  rotate7
  notifempty
}
```

**执行结果**

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603221044.png" style="zoom:80%;" />

#### 13.4.6 日志轮替机制

日志轮替之所以可以在指定的时间备份日志，是依赖系统定时任务。在 `/etc/cron.daily/`目录，就会发现这个目录中是有 `logrotate文件(可执行)，logrotate`通过这个文件依赖定时任务执行的。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603222408.png)

### 13.5 查看内存日志

1、常用命令

| 命令参数                                  | 参数说明                             |
| ----------------------------------------- | ------------------------------------ |
| journalctl                                | 可以查看全部内存日志，重启清空       |
| journalctl -n 3                           | 查看最新 3 条                        |
| journalctl --since 19:00 --until 19:10:10 | 查看起始时间到结束时间的日志可加日期 |
| journalctl -p err                         | 报错日志                             |
| journalctl -o verbose                     | 日志详细内容                         |
| journalctl _PID=1245 _COMM=sshd           | 查看包含这些参数的日志               |

2、案例说明

使用 `journalctl | grep sshd`来看看用户登录清空, 重启系统

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210603224343.png)

## 14-Linux备份与恢复

###  14.1 基本介绍

实体机无法做快照，如果系统出现异常或者数据损坏，后果严重， 要重做系统，还会造成数据丢失。所以可以使用备份和恢复技术。

linux 的备份和恢复有两种方式：

- 把需要的文件(或者分区)用`tag`打包就行，下次需要恢复的时候，再解压开覆盖即可。
- 执行 `dump` 和 `restore` 命令，进行操作。

### 14.2 安装 dump 和 restore

查看CentOS上没有 `dump` 和 `restore `指令，如果没有安装，则需要执行以下命令

dump安装

```shell
yum -y install dump
```

restore安装

```shell
yum -y install restore
```

###  14.3 dump 完成备份

#### 14.3.1 基本介绍

`dump` 支持分卷和增量备份(所谓增量备份是指备份上次备份后 修改/增加过的文件，也称差异备份）。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210604150303.png" style="zoom:80%;" />

#### 14.3.2 基本语法

```shell
dump [ -cu] -0123456789 [ -f <备份后文件名>] [-T <日期>] [ 目录或文件系统]
```

| 参数               | 具体作用                                                     |
| ------------------ | ------------------------------------------------------------ |
| - c                | 创建新的归档文件，并将由一个或多个文件参数所指定的内容写入归档文件的开头。 |
| - 0123456789       | 备份的层级。0 为最完整备份，会备份所有文件。若指定 0 以上的层级，则备份至上一次备份以来修改或新增的文件。<br/>到 9 后，可以再次轮替。 |
| - f <备份后文件名> | 指定备份后文件名。                                           |
| -j                 | 调用 bzlib 库压缩备份文件，也就是将备份后的文件压缩成 bz2 格式，让文件更小。 |
| -T <日期>          | 指定开始备份的时间与日期                                     |
| -u                 | 备份完毕后，在/etc/dumpdares 中记录备份的文件系统，层级，日期与时间等。 |
| -t                 | 指定文件名，若该文件已存在备份文件中，则列出名称             |
| -W                 | 显示需要备份的文件及其最后一次备份的层级，时间 ，日期。      |
| -w                 | 与-W 类似，但仅显示需要备份的文件。                          |

#### 14.3.3 应用案例

1、将/boot 分区所有内容备份到`/opt/boot.bak0.bz2 `文件中，备份层级为`0`

```shell
dump -0uj -f /opt/boot.bak0.bz2 /boot
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210604151115.png)

2、在/boot 目录下增加新文件，备份层级为“1”(只备份上次使用层次“0”备份后发生过改变的数据)，在/boot中创建`spring.java`文件。

```shell
dump -1uj -f /opt/boot.bak1.bz2 /boot
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210604152137.png)

#### 14.3.4 dump -W

显示需要备份的文件及其最后一次备份的层级，时间 ，日期。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210604152424.png)

#### 14.3.5 查看备份时间文件

执行命令：`cat /etc/dumpdates`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210604152702.png)

#### 14.3.6 备份文件或者目录

在备份分区时，是可以支持增量备份的，如果备份文件或者目录，不再支持增量备份, 即只能使用 0 级别备份

1、使用 dump 备份 /etc 整个目录

```shell
dump -0j -f /opt/etc.bak.bz2 /etc/
```

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210604155738.png)	

2、使用下面这条语句会报错。

```shell
dump -1j -f /opt/etc.bak.bz2 /etc/
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210604160058.png)

### 14.4 restore完成恢复

#### 14.4.1 基本介绍

restore 命令用来恢复已备份的文件，可以从 dump 生成的备份文件中恢复原文件

#### 14.4.2 基本语法

注意: 下面四个模式， 不能混用，在一次命令中， 只能指定一种。

| restore [模式选项] [选项] | 具体作用                                                     |
| ------------------------- | ------------------------------------------------------------ |
| -C                        | 使用对比模式，将备份的文件与已存在的文件相互对比。           |
| - i                       | 使用交互模式，在进行还原操作时，restors 指令将依序询问用户。 |
| - r                       | 查看模式，看备份文件有哪些文件。                             |
| -f <备份设备>             | 从指定的文件中读取备份数据，进行还原操作。                   |

#### 14.4.3 命令比较模式

restore 命令比较模式，比较备份文件和原文件的区别。

1、执行命令`mv /boot/spring.java /boot/spring1.java`

```shell
restore -C -f boot.bak1.bz2 
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210604190903.png)

2、执行命令`mv /boot/spring1.java /boot/spring.java`

```shell
restore -C -f boot.bak1.bz2
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210604194304.png)

#### 14.4.4 命令查看模式

restore 命令查看模式，看备份文件有哪些数据/文件

1、在`/opt`目录下创建一个`boots`文件夹。

2、执行命令：`restore -r -t /opt/boot.bak0.bz2 `。

3、执行命令: `restore -r -f /opt/boot.bak0.bz2 `

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210604200808.png" style="zoom:80%;" />

#### 14.4.5 命令还原模式

如果有增量备份，需要把增量备份文件也进行恢复， 有几个增量备份文件，就要恢复几个，按顺序来恢复即可。

1、在`/opt`目录下创建一个`bootttmp`文件夹。

2、恢复到第 1 次完全备份状态

```shell
restore -r -f /opt/boot.bak0.bz2
```

3、恢复到第 2 次增量备份状态

```shell
restore -r -f /opt/boot.bak1.bz2
```

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210604213524.png" style="zoom:80%;" />

## 15-Linux网络修改

### 15.1 查询网络

#### 15.1.1 网络状态查看

CentOS 7 .x系统默认没有安装 ifconfig命令,如果直接运行 **ifconfig** 命令，则提示错误 ：

```css
-bash: ifconfig: command not found
```

可以通过yum安装net-tools。

```css
yum install net-tools
```

安装后，`ifconfig` 命令可以正常执行。可以查看`/sbin` 目录，此时 ifconfig 文件也出现了。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605205014.png)

#### 15.1.2 显示网络设备命令

1、执行命令`ifconfig`

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605205238.png)

2、执行命令`ip addr ls`

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605205444.png" style="zoom:80%;" />

#### 15.1.3 网络接口

CentOS 7 .x系统使用了一致性网络设备命名，以上都不匹配才使⽤eth0，想要应用eth0，可以修改网络接口命名。

- `eno1`: 板载⽹网卡。
- `ens33`: PCI-E⽹网卡。
- `enp0s3`: 无法获取物理信息的 PCI-E网卡。
- `eth0`: 第一块⽹网卡(网络接⼝)

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605205527.jpg)

#### 15.1.4 修改网络接口命名

1、网卡命名规则受 biosdevname 和 net.ifnames 两个参数影响。

| 网络接口 | biosdevname | net.ifnames | 网卡名 |
| -------- | ----------- | ----------- | ------ |
| 默认接口 | 0           | 1           | ens33  |
| 接口1    | 1           | 0           | em1    |
| 接口2    | 0           | 0           | eth0   |

2、编辑 /etc/default/grub ⽂文件，增加 ==biosdevname=0 net.ifnames=0==

```css
vim /etc/default/grub
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605205938.jpg)



编辑文档：

```shell
GRUB_TIMEOUT=5
GRUB_DISTRIBUTOR="$(sed 's, release .*$,,g' /etc/system-release)"
GRUB_DEFAULT=saved
GRUB_DISABLE_SUBMENU=true
GRUB_TERMINAL_OUTPUT="console"
GRUB_CMDLINE_LINUX="crashkernel=auto rd.lvm.lv=centos/root rd.lvm.lv=centos/swap rhgb quietbiosdevname=0 net.ifnames=0"
GRUB_DISABLE_RECOVERY="true"
```

3、更新grub

```css
grub2-mkconfig -o /boot/grub2/grub.cfg
```

4、重新启动

```css
reboot
```

#### 15.1.5 查看网络

执行命令`mii-tool eth0`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605210124.jpg)

#### 15.1.6 查看网关

执行命令：`route -n`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605210451.jpg)

### 15.2 网络配置

#### 15.2.1 修改ip地址和子网掩码

1、基本语法

```shell
ifconfig <接口> <IP地址> [netmask 子网掩码 ]
```

2、查询IP地址

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605210601.jpg)

3、修改操作

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605210719.jpg)

#### 15.2.2 开启网卡和关闭网卡

- `ifup`<网络接口>: 开启网卡
- `ifdown`<网卡接口>：关闭网卡

### 15.3 网关配置

#### 15.3.1 添加网关

1、基本语法

```css
route add default gw <⽹网关ip>
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605210946.jpg)

#### 15.3.2 添加明细路由

1、基本语法

```css
route add -host <指定ip> gw <网关ip>
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605211141.jpg)

#### 15.3.3 设置网段明细路由

1、基本语法

```css
route add -net <指定⽹网段> netmask <子网掩码> gw <网关ip>
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605211231.jpg)

#### 15.3.4 网络故障排除

常用命令！！！

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605211329.png" style="zoom: 50%;" />



### 15.4 网络服务的管理

linux中常见的网络服务相关的命令如下

| **命令**                      | **说明**         |
| ----------------------------- | ---------------- |
| **systemctl start network**   | 开启网络服务     |
| **systemctl stop network**    | 停止网络服务     |
| **systemctl restart network** | 重启网络服务     |
| **systemctl status network**  | 显示网络服务状态 |

#### 15.4.1 查看当前网络状态

1、执行命令: `systemctl status network`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605211512.jpg)

#### 15.4.2 设置静态IP地址

1- 查看当前网卡名称: `ifconfig`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605211618.jpg)

**注意：**`centos7`的网络IP地址配置文件在 ==/etc/sysconfig/network-scripts== 文件夹下，`ens33`网卡对应的配置文件为`ifcfg-ens33`。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605211743.jpg)

2、修改`ifcfg-ens33`的内容

```css
vim /etc/sysconfig/network-scripts/ifcfg-ens33 

BOOTPROTO="static"         # 使用静态IP地址，默认为dhcp
IPADDR="192.168.222.128"   # 设置的静态IP地址
NETMASK="255.255.255.0"    # 子网掩码
GATEWAY="192.168.222.2"    # 网关地址
DNS1="192.168.222.2"       # DNS服务器
```

3、修改后一定要重启服务

- 重启网络: `systemctl restart network`

- 重启系统：`reboot `


## 16-Linux修改内核

### 16.1 升级内核版本

查看内核的版本

```shell
uname -r
```

升级内核两种方式

### 16.2 yum 安装

1、安装epel软件包

```shell
yum install epel-release -y
```

2、安装最新版内核

```shell
yum install kernel
```

### 16.3 源代码编译安装内核

#### 16.3.1 安装需要的依赖包

```shell
yum install gcc gcc-c++ make ncurses-devel openssl-devel elfutils-libelf-devel -y
```

#### 16.3.2 下载并且解压缩内核

[inux内核下载](https://www.kernel.org/)

**解压：**

```shell
tar xvf linux-5.6.7.tar.xz -C /usr/src/kernels/
```

#### 16.3.3 配置内核编译参数

1、执行以下命令

```shell
cd /usr/src/kernels/linux-5.6.7/
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605213631.jpg)

```shell
make menuconfig 
```

2、出现错误：inux-内核导入配置 `lexer.lex.c`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605213704.jpg)

3、解决方案：

```css
yum install bison -y
yum install flex -y
```

#### 16.3.4 使用当前系统内核配置

1、进入File Systems，==使内核支持NTFS==这个文件系统。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605213739.jpg" style="zoom:80%;" />

2、进入DOS/FAT/NT文件系统。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605213739.jpg)

3、内核支持NTFS写入操作。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605214914.jpg)

4、默认保存，然后一路退出操作

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605214950.jpg)

5、查看内核的具体参数，多了一个.config的文件。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605215017.jpg)

6、进入/boot目录查看现在使用的内核，将config进行覆盖，然后重命名为`.config`

```shell
cd /bootcp config-3.10.0-1062.18.1.el7.x86_64 /usr/src/kernels/linux-5.6.7/.config
```

7、编译和安装内核

编译内核：`make -j2 all`

安装内核：

```css
make modules_install(安装内核模块)make install
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605215141.jpg)

8、查看内核版本

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605215238.jpg)

## 17-Linux其他

### 17.1 找回mysql用户密码

1、执行`mysql -u root -p`指令

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605014502.png)

2、执行命令`vim /etc/my.cnf`，添加语句`skip-grant-tables`

<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605014645.png" style="zoom:80%;" />	

3、执行该命令`service mysqld restart`。

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605014856.png)

4、无需密码，直接登录。

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605015101.png" style="zoom:80%;" />

5、使用数据库，查看数据表。

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605015243.png)

6、修改密码

```sql
update user set authentication_string=password("root") where user='root';
```

![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605015427.png)

7、执行刷新操作！！！

```shell
flush privileges;
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605015653.png)

8、执行`mysql -u root -p`命令，输入密码，登入成功！！！

​	<img src="https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605015925.png" style="zoom: 80%;" />

9、注销操作，执行命令`vim /etc/my.cnf`

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605020045.png)

### 17.2 修改CentOS默认yum源

有时候CentOS默认的yum源不一定是国内镜像，导致yum在线安装及更新速度不是很理想。需要将yum源设置为国内镜像站点。

#### 17.2.1 腾讯源

1.备份系统旧配置文件

```
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
```

2、进入yum源配置文件所在的文件夹

```shell
[root@linux ~]# cd /etc/yum.repos.d/
```

3、下载==**mirrors.tencentyun.com**==的yum源配置文件到上面那个文件夹内

> **CentOS5**

```css
wget -O /etc/yum.repos.d/CentOS-Base.repo http:/mirrors.tencentyun.com/repo/centos5_base.repo
```

> **CentOS6**

```css
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.tencentyun.com/repo/centos6_base.repo
```

> **CentOS7**

```css
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.tencentyun.com/repo/centos7_base.repo
```

> **CentOS8**

```css
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.tencentyun.com/repo/centos8_base.repo
```

> **更新缓存**

```css
yum clean allyum makecacheyum -y update
```

#### 17.2.2 阿里源

1.备份系统旧配置文件

```
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
```

2、进入yum源配置文件所在的文件夹

```shell
[root@linux ~]# cd /etc/yum.repos.d/
```

3、下载==mirrors.aliyun.com==的yum源配置文件到上面那个文件夹内

> **CentOS5**

```css
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-5.repo
```

> **CentOS6**

```css
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-6.repo
```

> **CentOS7**

```css
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
```

> **CentOS8**

```css
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-8.repo
```

> **更新缓存**

```css
yum clean allyum makecacheyum -y update
```

### 17.3 普通用户和root用户切换

1、**[linux@guardwhy ~]$**：linux表示当前用户，guardwhy表示主机名，$表示普通用户。**[root@guardwhy ~]#** ：root表示root用户,#表示在超级用户下输入命令。

2、输入命令： su  - ,此时输入root用户的密码

```css
su - :切换到超级用户
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605213349.jpg)

3、root用户切换成普通用户。

```css
su - linux
```

4、普通用户重新切换成root用户。

```css
输入命令:exit，直接切换成root用户，不在输入密码
```

​	![](https://guardwhy.oss-cn-beijing.aliyuncs.com/img/javaEE/SpringMVC/Test4/20210605213423.jpg)

