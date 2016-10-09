## DOL配置

作者：林佩诗

学号：14353181

### Discription

**The distributed operation layer (DOL)** is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.

### How to install

* 安装必要环境

$ sudo apt-get update

![1.png](https://github.com/Pacylinpeishi/ES2016_14353181/blob/master/1.png?raw=true)

$ sudo apt-get install ant

![2.png](https://thumbnail0.baidupcs.com/thumbnail/3f78180d243e695715809aeb495aa38e?fid=2694813189-250528-557590042374746&time=1475992800&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-ii7BNxyrOaNB2YgDCs%2Fej6AGsCA%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6554658485904464297&dp-callid=0&size=c710_u400&quality=100)

$ sudo apt-get install openjdk-7-jdk

![3.png](https://thumbnail0.baidupcs.com/thumbnail/2c0ba30494312576d03f4c158eb4a4f6?fid=2694813189-250528-1018896226882832&time=1475992800&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-WySUQHgIWo1UeoMWLVzSXDo2OdM%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6554728871844489742&dp-callid=0&size=c710_u400&quality=100)

$ sudo apt-get install unzip

![4.png](https://thumbnail0.baidupcs.com/thumbnail/166dbf72167a4ed3571fc6a57029a1cb?fid=2694813189-250528-310394251080201&time=1475992800&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-Qexh%2BiqF0qfS2KwjWBZWuZH9cRQ%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6554762697360825764&dp-callid=0&size=c710_u400&quality=100)

* 解压文件

新建dol文件夹: $ mkdir dol

![5.png](https://thumbnail0.baidupcs.com/thumbnail/5f72e7f0be15affc5a55f0b99bbf6f57?fid=2694813189-250528-328048248441336&time=1475992800&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-ED5Xq3SZ5LodlI%2BzuDeQrWWUYFQ%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6554806260679929158&dp-callid=0&size=c710_u400&quality=100)

将dolethz.zip解压到 dol文件夹中: $ unzip dol_ethz.zip -d dol

![6.png](https://thumbnail0.baidupcs.com/thumbnail/b05731dfa5cb35f7860bb5797b1152f2?fid=2694813189-250528-241403378617688&time=1475992800&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-G2MwEPkLZlLuYfaObfyp7pNZSII%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6554841382514082747&dp-callid=0&size=c710_u400&quality=100)

解压systemc: $ tar -zxvf systemc-2.3.1.tgz

![7.png](https://thumbnail0.baidupcs.com/thumbnail/119d2dde6a5e5e97cc827ad0615909b9?fid=2694813189-250528-391850785469739&time=1475992800&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-V%2Blt0QxFIRiCTOddhuZh0bc4iCI%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6554870649823516074&dp-callid=0&size=c710_u400&quality=100)
![8.png](https://thumbnail0.baidupcs.com/thumbnail/4711c0ada40291412219a173ae729dff?fid=2694813189-250528-816795312220631&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-0KgG2a7cc3vs0A0tT4WM4UJEnZI%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6554887811098557884&dp-callid=0&size=c710_u400&quality=100)

* 编译systemc

解压后进入systemc-2.3.1的目录下： $ cd systemc-2.3.1

![9.png](https://thumbnail0.baidupcs.com/thumbnail/89e78a61c538fbd1ffd90f53b4be6d5f?fid=2694813189-250528-974576109864905&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-HQOmQtWdeSeijhBO%2FIrQf3d%2FYx4%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6554954902582063497&dp-callid=0&size=c710_u400&quality=100)

新建一个临时文件夹objdir: $ mkdir objdir

![10.png](https://thumbnail0.baidupcs.com/thumbnail/b05522535cbb292ceacd67e76e25ba05?fid=2694813189-250528-641508310697819&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-5onnWjSsJBQtX9NBSR%2BkAj6knmQ%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6554985839118573470&dp-callid=0&size=c710_u400&quality=100)

进入该文件夹objdir: $ cd objdir

![11.png](https://thumbnail0.baidupcs.com/thumbnail/8190e61715d514071716eb8bded644d2?fid=2694813189-250528-940963086965529&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-0icIJQzz6b5xn0OAh1jvLNEBM6M%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555033427689573810&dp-callid=0&size=c710_u400&quality=100)

运行configure(能根据系统的环境设置一下参数，用于编译): $ sudo ../configure CXX=g++ --disable-async-updates，但输入命令运行后出现以下错误：

![12.png](https://thumbnail0.baidupcs.com/thumbnail/cb663262fb72b11ddc893accfb2f8033?fid=2694813189-250528-1057302925068817&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-S0NQwpU4RL2sFxCBWF%2BSueDbLIA%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555123087516325599&dp-callid=0&size=c710_u400&quality=100)

研究错误信息，发现应该是gcc编译环境没有配置好，接下来就安装gcc: $ sudo apt-get install build-essential

![13.png](https://thumbnail0.baidupcs.com/thumbnail/cb663262fb72b11ddc893accfb2f8033?fid=2694813189-250528-650497300816487&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-8zWW44BYWfpBG61OrRFCRNVtqBY%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555275175029604528&dp-callid=0&size=c710_u400&quality=100)

$ sudo apt-get install gcc libc6-dev

![14.png](https://thumbnail0.baidupcs.com/thumbnail/a5fce77e6f8ee41bdb15729297825e15?fid=2694813189-250528-102442702502990&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-ppVHmuCT06YfxWA9Y8pocsp8oMg%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555297900211483390&dp-callid=0&size=c710_u400&quality=100)

重新进入到systemc-2.3.1/objdir/文件夹下,再configure一次就成功了: $ sudo ../configure CXX=g++ --disable-async-updates

![15.png](https://thumbnail0.baidupcs.com/thumbnail/e73ffb5c471539027036500bbab19933?fid=2694813189-250528-15247201186234&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-76JLuQz7v44iuHj406L1tagCdc8%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555348865874911737&dp-callid=0&size=c710_u400&quality=100)

编译： $ sudo make install,但是命令执行之后出现如下错误

![16.png](https://thumbnail0.baidupcs.com/thumbnail/40ae04654b139906d004a95890be3fd2?fid=2694813189-250528-917162456737349&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-inJ6d2fZKbA9FktL5znXzvtizyM%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555400158020707946&dp-callid=0&size=c710_u400&quality=100)

这种情况有时候是因为工程所在的目录改变，我在编译的时候直接在systemc文件下编译，而systemc下没有makefile文件，要在objdir文件里才有，由于擅自改变了工程目录，而makefile里面的.h文件路径没有改变，所以出现来了这种错误。解决办法是进入objdir文件夹下面再$ sudo make install

![17.png](https://thumbnail0.baidupcs.com/thumbnail/24eae2b783e057207f6e8b2873b7ba1b?fid=2694813189-250528-525933024154016&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-CjqlR80%2FciizcHJk89tLEykHE7k%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555432712065654355&dp-callid=0&size=c710_u400&quality=100)

编译完后检查systemc-2.3.1文件的目录： $ ls

![18.png](https://thumbnail0.baidupcs.com/thumbnail/e01b85990c2ed61abaca8b782a20c734?fid=2694813189-250528-204751494415703&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-K%2Bn5OBHQt5SXRalHIhcHtyf5thU%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555470466052024588&dp-callid=0&size=c710_u400&quality=100)

记录当前的工作路径(会输出当前所在路径，记下来，待会有用,这里表示我的工作路径为/home/linpeishi/systemc-2.3.1): $ pwd

![19.png](https://thumbnail0.baidupcs.com/thumbnail/26f7d40835e92b69f74441658c7afb86?fid=2694813189-250528-66600965335064&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-ZK5%2BG4YJnCZvDj9RQoxAr2Ftnj4%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555492124598721828&dp-callid=0&size=c710_u400&quality=100)

* 编译dol

进入刚刚dol的文件夹： $ cd ../dol

![20.png](https://thumbnail0.baidupcs.com/thumbnail/5672f21d0d551cfe1ac92e40df3c8075?fid=2694813189-250528-318704807601337&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-3GJtQ0fNVWqWgtTX3F0pTrpSjBU%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555527065166021383&dp-callid=0&size=c710_u400&quality=100)

修改build_zip.xml文件,首先要安装gedit(新版本的ubuntu内含）: $ sudo apt-get install gedit

![21.png](https://thumbnail0.baidupcs.com/thumbnail/3ed178ff3466d4919fe326e3d6dde6b5?fid=2694813189-250528-29226990294755&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-DOFtIBfBP5bw8F%2FYimgasxfXZOg%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555606454406152524&dp-callid=0&size=c710_u400&quality=100)

用gedit打开xml文档,然后将找到下面这段话： $ sudo gedit build_zip.xml

![22.png](https://thumbnail0.baidupcs.com/thumbnail/51e1f67d3744df69690c588d902e7ce9?fid=2694813189-250528-269364334426113&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-73gh2qebRdQn4KjrMgOH2pS61sI%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555637390579181198&dp-callid=0&size=c710_u400&quality=100)

按照之前pwd得出来的路径修改

![23.png](https://thumbnail0.baidupcs.com/thumbnail/5c9abb2eebb6468bdbce8070e1039c8f?fid=2694813189-250528-404979665245797&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-N1%2FsbkCIwzHj%2BvQwTmHLpa7nbs8%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555733637269582910&dp-callid=0&size=c710_u400&quality=100)

然后编译: $ ant -f build_zip.xml all

![24.png](https://thumbnail0.baidupcs.com/thumbnail/95eb5115494a292d44f71594aecdcd8a?fid=2694813189-250528-1028231432207180&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-dKNvUCXo5VcO5yorBmF7LapLBTs%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555764424949915979&dp-callid=0&size=c710_u400&quality=100)

接着可以试试运行第一个例子,进入build/bin/mian路径下,然后运行第一个例子： $ ant -f runexample.xml -Dnumber=1

![25.png](https://thumbnail0.baidupcs.com/thumbnail/4e4bfb4551cd0901e77c13c3149fbc07?fid=2694813189-250528-525888257254132&time=1475996400&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-DHDQ0dfWBkz6HVRmnOeM%2F63f%2Bfw%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6555827889782714070&dp-callid=0&size=c710_u400&quality=100)

以上，关于ubuntu的DOL环境配置成功。

### Experimental experience

这次实验是基于了上一次实验记录下来的DOL配置过程，再加上了对git的运用。实验过程中出现的问题是，上一周配置好的虚拟机由于内存等原因不能开启，所以为了进度就重新配置一个虚拟机，在这过程上消耗了比较多的时间，但是因为有了之前没有遇到过的错误的出现，让我更加理解了这个配置的过程。在本周的实验中我参考了比较多的是廖雪峰的官方网站，里面有比较多的知识，加深了我对版本控制的理解。



