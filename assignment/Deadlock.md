##Lab4-Deadlock

###【个人信息】

姓名：林佩诗

学号：14353181

完成日期：2016/10/18

###【实验步骤】
1. 按要求编写Deadlock.java文件，保存到虚拟机的一个文件夹中。

2. 在终端进入到这个文件夹，然后运行命令：$ javac Deadlock.java

3. 在这个文件夹中新建一个文件“Deadlock”，按要求编写内容，然后到终端运行，命令如下：$ sudo chomd 777 Deadlock，获得权限后再运行：$ ./Deadlock

4. 发现程序跑了一百遍，但是没有发生死锁，接着在调节程序中修改count的值，改成“count=?"，使其发生死锁。如下图所示：

![2.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/lab4_image/2.png?raw=true)

###【实验问题】

1. 产生死锁的4个必要条件：

①互斥条件：一个资源每次只能被一个进程使用；

②请求与保持条件：一个进程因请求资源而阻塞时，对已获得的资源保持不放；

③不剥夺条件:进程已获得的资源，在末使用完之前，不能强行剥夺；

④循环等待条件:若干进程之间形成一种头尾相接的循环等待资源关系。


2. 上述程序产生死锁的解释：

在Deadlock函数中的t.start()执行后，线程t就被插入到调度队列当中，当调度到他的时候，就跑run()里面的代码，run()里面执行b.methodB(a)，再看methodB(a)函数，是用synchronized来修饰的，用这个方法声明函数的时候保证在同一时刻最多只有一个线程执行这段代码（输出“Inside a.last()”）。回到Deadlock函数，在执行t.start()之后，用while循环等待count个时间单位之后执行a.method(b)，这个函数也是用synchronized声明的，用于输出“Inside B.last()”，但是当一个线程访问object的一个synchronized同步代码块的时候，其他线程对object中所有其他synchronized同步代码块的访问就会被阻塞。如下图为Deadlock.java的完整的代码，结合代码分析上述内容：

![3.PNG](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/lab4_image/3.PNG?raw=true)

![4.PNG](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/lab4_image/4.PNG?raw=true)

所以如果我们调整等待时间count的值，使执行a.methodA(b)和b.methodB(a)的时间差不多，那么就会发生死锁了。如下图为解析图：

![1.PNG](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/lab4_image/1.PNG?raw=true)


###【实验感想】

这次实验比较简单，运用到了上学期我们学习操作系统的时候的一个概念“死锁”，其中synchronized可以用临界区的原理来理解，它保证了在同一时刻最多只有一个线程执行这段代码，如果在同意时刻还有其他用synchronized定义的代码想访问object的话就会被阻塞。这次实验需要修改的部分就是count的值，通过修改count的值，使得执行a.methodA(b)和b.methodB(a)的时间差不多，形成死锁的现象。