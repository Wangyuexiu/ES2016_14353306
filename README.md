# 配置DOL
***
##### 1、安装必要的环境
在终端输入如下语句：  

    sudo apt-get update
    sudo apt-get install ant
    sudo apt-get install openjdk-7-jdk 
    sudo apt-get install unzip
下载完安装包，对压缩包进行解压。

    sudo mkdir dol
    sudo unzip dol_ethz.zip -d dol
    sudo tar -zxvf systemc-2.3.1.tgz
解压后进入目录，新建并运行configure：

    cd systemc-2.3.1
    sudo mkdir objdir
    cd objdir
    sudo ../configure CXX=g++ --disable-async-updates
运行结果如下图所示：
![N|Solid](http://p1.bqimg.com/567571/96e0e2928cf0399d.png)
继续完成编译systemc，然后纪录下当前的工作路径

    sudo make install
    sudo pwd
然后进入dol的文件夹，手动修改build_zip.xml文件。然后编译被修改的这份文件。

    sudo ant -f build_zip.xml all
运行结果如下：
![N|Solid](http://p1.bpimg.com/567571/baedf05b10811d5a.png)
进入build/bin/mian路径下，运行第一个例子。

    cd build/bin/main
    ant -f runexample.xml -Dnumber=1
运行成功结果如下：
![N|Solid](http://p1.bpimg.com/567571/25096da522556b13.png)


