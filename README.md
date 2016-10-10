## Description
> The distributed operation layer (DOL) is a software development framework to program parallel applications. 
The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. 
Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.

![](http://i.imgur.com/hes8ikW.png)
##  How to install
1.首先需要配置好以下四种环境：

* C/C++ environment
* Java environment
* Build environment
* SystemC envifronment

2.解压DOL文件，修改build_zip.xml文件后即可编译安装DOL


### 1. Environment
#### (1)C/C++ environment: compiler, linker
	$ sudo apt-get update       
   	$ sudo apt-get install g++
#### (2)Java environment: javac, java
	$ sudo apt-get install openjdk-7-jdk
#### (3)Build environment: make, Ant (version 1.6.5 or greater)
 	$ sudo apt-get install ant
	$ sudo apt-get install unzip
#### (4)SystemC envifronment (version 2.1 or greater)


##### 4.1 解压systemc
	$ tar -zxvf systemc-2.3.1.tgz

##### 4.2 解压后进入systemc-2.3.1的目录下
	$ cd systemc-2.3.1
##### 4.3 新建一个临时文件夹objdir
	$ mkdir objdir
##### 4.4 进入该文件夹objdir
	$ cd objdir
##### 4.5 运行configure(能根据系统的环境设置一下参数，用于编译)
	$ ../configure CXX=g++ --disable-async-updates

![](http://i.imgur.com/uccWP5d.png)
##### 4.6 编译systemc
	$ sudo make install
编译完后文件目录如下：
![](http://i.imgur.com/dE670qF.png)
##### 4.7 记录当前的工作路径
	$ pwd
可以看到当前工作路径为：
![](http://i.imgur.com/HQN6xVp.png)




### 2. DOL
#### (1)新建dol的文件夹 
	$ mkdir dol
#### (2)将dolethz.zip解压到 dol文件夹中
	$ unzip dol_ethz.zip -d dol
#### (3)进入刚刚dol的文件夹，修改build_zip.xml文件 
	$ mkdir dol
#### (4)将dolethz.zip解压到 dol文件夹中
	$ unzip dol_ethz.zip -d dol
#### (5)修改build_zip.xml文件
	找到下面内容：
	<property name="systemc.inc" value="YYY/include"/>
	<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
	把YYY改成上页pwd的结果（对于64位系统的机器，lib-linux要改成lib-linux64）
#### (6)编译DOL
	$ ant -f build_zip.xml all
#### (7)运行例子查看结果
	$ cd build/bin/main
 	$ ant -f runexample.xml -Dnumber=1

成功会出现如下结果：
![](http://i.imgur.com/tVgJApn.png)


## Experimental experience
> 按照教程一步一步进行操作即可。注意正确记录systemc所在的工作路径。
