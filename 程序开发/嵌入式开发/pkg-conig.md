# PKG-config 工具使用指南

pkg-config 是一种外部库管理工具，可以方便的管理定义外部库（如opencv）

* 在包的相关信息储存在××.pc文件下，pkg-config 通过查找其环境变量中的 `$PKG_CONFIG_PATH` 来寻找想要的包的信息文件，我目前的pkg-config 路径在电脑的/usr/locl/libs 里（管理一个库其实就是管理库的头文件，动态和静态库文件，这些信息都在.pc 中，所以一旦安装了库，想要改变路径，也必须改变.pc文件相应信息）
* pkg-config 的使用非常方便，在使用gcc/g++编译文件时，需要用到的参数只需要使用pkg-config 生成的库变量即可 如： `g++ $(pkg-config --cflags --libs opencv2.pc) -o test1 test1.cpp` 非常实用方便