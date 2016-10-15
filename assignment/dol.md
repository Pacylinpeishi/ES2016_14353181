##Lab3-DOL实例分析&编程

###【个人信息】

姓名：林佩诗

学号：14353181

完成日期：2016/10/15

###【实验任务】

1. 修改example1,使其输出3次方数

2. 修改example2，让3个square模块变成2个

###【实验结果】


需要注意的是，要打开.dot文件查看的实验结果的话要安装xdot，命令为：$ sudo apt-get install xdot

* 修改example1之后的example1.dot图

![3.PNG]()

* 修改example2之后的example2.dot图

![8.PNG]()


###【实验步骤】

* 修改example1

打开example1中的src文件,路径是dol/example/example1/src，修改里面的square.c函数，找到“i=i*i”，将二次方改成三次方。修改后的结果如下图所示

![1.PNG]()

编译dol，编译成功的话会出现“BUILD SUCCESSFUL”，命令为：$ ant -f build_zip.xml all，运行结果如下：

![4.PNG]()

再打开main文件夹，路径是dol/build/bin/main，删掉之前编译出来的example1，便于得到新的结果。然后运行第一个例子：$ ant -f runexample.xml -Dnumber=1，运行结果如下：

![2.PNG]()


* 修改example2

用gedit打开example2中的example2.xml文件,路径是dol/example/example2,命令是：$ sudo gedit example.xml，修改里面的variable，找到“value="3"”，将3改成2。修改后的结果如下图所示:

![5.PNG]()

编译dol，编译成功的话会出现“BUILD SUCCESSFUL”，命令为：$ ant -f build_zip.xml all，运行结果如下：

![6.PNG]()

再打开main文件夹，路径是dol/build/bin/main，删掉之前编译出来的example2，便于得到新的结果。然后运行第一个例子：$ ant -f runexample.xml -Dnumber=2，运行结果如下：

![7.PNG]()

###【实验感想】

这次实验比较简单，主要是对dol额两个实例做了简单的修改和分析。虽然过程不复杂，但是对于实例中代码的分析和理解才是这次实验的真正目的，根据课件上面的介绍，就能大概理解当中额思路了。






