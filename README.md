## DOL配置

作者：林佩诗

学号：14353181

### Discription

**The distributed operation layer (DOL)** is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.

### How to install

* 安装必要环境

$ sudo apt-get update

![1.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/1.png?raw=true)

$ sudo apt-get install ant

![2.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/2.png?raw=true)

$ sudo apt-get install openjdk-7-jdk

![3.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/3.png?raw=true)

$ sudo apt-get install unzip

![4.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/4.png?raw=true)

* 解压文件

新建dol文件夹: $ mkdir dol

![5.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/5.png?raw=true)

将dolethz.zip解压到 dol文件夹中: $ unzip dol_ethz.zip -d dol

![6.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/6.png?raw=true)

解压systemc: $ tar -zxvf systemc-2.3.1.tgz

![7.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/7.png?raw=true)

![8.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/8.png?raw=true)

* 编译systemc

解压后进入systemc-2.3.1的目录下： $ cd systemc-2.3.1

![9.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/9.png?raw=true)

新建一个临时文件夹objdir: $ mkdir objdir

![10.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/10.png?raw=true)

进入该文件夹objdir: $ cd objdir

![11.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/11.png?raw=true)

运行configure(能根据系统的环境设置一下参数，用于编译): $ sudo ../configure CXX=g++ --disable-async-updates，但输入命令运行后出现以下错误：

![12.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/12.png?raw=true)

研究错误信息，发现应该是gcc编译环境没有配置好，接下来就安装gcc: $ sudo apt-get install build-essential

![13.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/13.png?raw=true)

$ sudo apt-get install gcc libc6-dev

![14.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/14.png?raw=true)

重新进入到systemc-2.3.1/objdir/文件夹下,再configure一次就成功了: $ sudo ../configure CXX=g++ --disable-async-updates

![15.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/15.png?raw=true)

编译： $ sudo make install,但是命令执行之后出现如下错误

![16.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/16.png?raw=true)

这种情况有时候是因为工程所在的目录改变，我在编译的时候直接在systemc文件下编译，而systemc下没有makefile文件，要在objdir文件里才有，由于擅自改变了工程目录，而makefile里面的.h文件路径没有改变，所以出现来了这种错误。解决办法是进入objdir文件夹下面再$ sudo make install

![17.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/17.png?raw=true)

编译完后检查systemc-2.3.1文件的目录： $ ls

![18.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/18.png?raw=true)

记录当前的工作路径(会输出当前所在路径，记下来，待会有用,这里表示我的工作路径为/home/linpeishi/systemc-2.3.1): $ pwd

![19.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/19.png?raw=true)

* 编译dol

进入刚刚dol的文件夹： $ cd ../dol

![20.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/20.png?raw=true)

修改build_zip.xml文件,首先要安装gedit(新版本的ubuntu内含）: $ sudo apt-get install gedit

![21.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/21.png?raw=true)

用gedit打开xml文档,然后将找到下面这段话： $ sudo gedit build_zip.xml

![22.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/22.png?raw=true)

按照之前pwd得出来的路径修改

![23.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/23.png?raw=true)

然后编译: $ ant -f build_zip.xml all

![24.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/24.png?raw=true)

接着可以试试运行第一个例子,进入build/bin/mian路径下,然后运行第一个例子： $ ant -f runexample.xml -Dnumber=1

![25.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/image/25.png?raw=true)

以上，关于ubuntu的DOL环境配置成功。

### Experimental experience

这次实验是基于了上一次实验记录下来的DOL配置过程，再加上了对git的运用。实验过程中出现的问题是，上一周配置好的虚拟机由于内存等原因不能开启，所以为了进度就重新配置一个虚拟机，在这过程上消耗了比较多的时间，但是因为有了之前没有遇到过的错误的出现，让我更加理解了这个配置的过程。在本周的实验中我参考了比较多的是廖雪峰的官方网站，里面有比较多的知识，加深了我对版本控制的理解。



