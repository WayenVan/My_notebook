# 安装交叉编译工具时候遇到的主要问题

在此列出安装交叉编译工具链 arm-linux-gcc 4.4.3 中遇到的主要步骤及问题

1. 将压缩文件包 arm-linux-gcc4.4.3.tar.gz 文件拷贝进入目录 `~/arm` 目录下
2. 运行解压命令 `tar -zxvf arm-linux-gcc4.4.3.tar.gz` 命令解压到当前目录中
3. 确定环境变量：用户bash文件 `~/.bash_profile` 是用户登录时会运行的bash文件，在其中输入 `export PATH=$PATH:~/arm/.../4.4.3/bin` 并且利用命令 `source ~/.bash_profile` 重新运行文件，之后再确定环境变量PATH目录有没有变化 `echo $PATH` 观察输出是否已经添加工具目录
4. 最后，运行 `arm-linux-gcc -v` 命令查看是否安装正确

* 如果linux系统是64位的，需要安装32位的库文件，具体百度
* 如果linux系统是64位的，还需要安装32位库文件，运行代码`apt-get install lib32stdc++6`



