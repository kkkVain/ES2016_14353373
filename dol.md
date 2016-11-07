## 任务要求
1.修改example2,让3个square模块变成2个

2.修改example1,让其输出3次方数

## 实验过程
1.实现方法

* 对于第一个任务，将example2.xml中N的值从“3”改为“2”

	![](http://i.imgur.com/VXcQuhe.png)

* 对于第二个任务，将example1/src中的square.c中i的赋值从"i*i"改为"i^3"

	![](http://i.imgur.com/6wkSKxm.png)

2.实验原理

* 第二个任务中，可以看出，example2.xml中通过迭代定义了3个square:

	![](http://i.imgur.com/02rOlZX.png)

	迭代的square个数由N控制，所以只要改变N的值即可。

* 第一个任务中，example1的square.c的square_fire()中，从PORT_IN读到的数做了平方后又写入了PORT_OUT,定义了平方运算，所以只要将读入的i进行三次方运算就可以把这个运算定义成立方运算。

	[](http://i.imgur.com/tQr9G3B.png)


3.实验后的.dot截图

* example1

	[](http://i.imgur.com/YJNeKAe.png)

* example2

	[](http://i.imgur.com/hkMOxvK.png)


## 实验感想
   认真理解课件上给出注释、说明的地方，通常都是关键点，明白之后完成实验任务就很容易了。