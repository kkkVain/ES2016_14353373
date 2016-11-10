## 任务要求
根据ros官网教程进行ROS配置。

## 实验过程
1.设置软件更新源sources.list，

	 sudo sh -c'echo“deb http://packages.ros.org/ros/ubuntu $（lsb_release -sc）main”> /etc/apt/sources.list.d/ros-latest.list'
2.设置密钥

	sudo apt-key adv --keyserver hkp：//ha.pool.sks-keyservers.net：80 --recv-key 0xB01FA116

这一步遇到了报错：
	![](http://i.imgur.com/4X2Pppq.png)

官网上 http://answers.ros.org/question/223702/ros-keyserver-down/ 有人提出类似问题。

解决方法是使用如下命令：

	wget https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -O - | sudo apt-key add -

![](http://i.imgur.com/HpceKVn.png)

3.同步最新的软件包列表

	sudo apt-get update

4.安装完全桌面版ROS，包括ROS，rqt，rviz，机器人通用库，2D / 3D模拟器，导航和2D / 3D观感

	sudo apt-get install ros-jade-desktop-full

5.初始化rosdep
	
	sudo rosdep init
	rosdep update

6.环境变量设置

	echo“source /opt/ros/jade/setup.bash”>>〜/ .bashrc
	source〜/ .bashrc

7.获取rosinstall

	sudo apt-get install python-rosinstall

8.测试ROS

	roscore

## 实验结果

使用roscore命令启动ROS，可以看出ROS成功启动。

![](http://i.imgur.com/WoEsvhb.png)
