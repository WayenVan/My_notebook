# Anaconda information 

## anaconda 镜像使用帮助：

添加镜像的命令：

```bash
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```

即可添加 Anaconda Python 免费仓库。

## anaconda 环境管理

设置一个环境如下：

```bash
# 创建一个名为python34的环境，指定Python版本是3.4（不用管是3.4.x，conda会为我们自动寻找3.4.x中的最新版本）
conda create --name python34 python=3.4
 
# 安装好后，使用activate激活某个环境
activate python34 # for Windows
source activate python34 # for Linux & Mac
# 激活后，会发现terminal输入的地方多了python34的字样，实际上，此时系统做的事情就是把默认2.7环境从PATH中去除，再把3.4对应的命令加入PATH
 
# 此时，再次输入
python --version
# 可以得到`Python 3.4.5 :: Anaconda 4.1.1 (64-bit)`，即系统已经切换到了3.4的环境
 
# 如果想返回默认的python 2.7环境，运行
deactivate python34 # for Windows
source deactivate python34 # for Linux & Mac
 
# 删除一个已有的环境
conda remove --name python34 --all
```
用户安装的不同python环境都会被放在目录~/anaconda/envs下，可以在命令中运行conda info -e查看已安装的环境，当前被激活的环境会显示有一个星号或者括号。

说明：有些用户可能经常使用python 3.4环境，因此直接把~/anaconda/envs/python34下面的bin或者Scripts加入PATH，去除anaconda对应的那个bin目录。这个办法，怎么说呢，也是可以的，但总觉得不是那么elegant……

如果直接按上面说的这么改PATH，你会发现conda命令又找不到了（当然找不到啦，因为conda在~/anaconda/bin里呢），这时候怎么办呢？方法有二：1. 显式地给出conda的绝对地址 2. 在python34环境中也安装conda工具（推荐）。

## anaconda 包管理

常用操作：

```bash
# 查看当前环境下已安装的包
conda list
 
# 查看某个指定环境的已安装包
conda list -n python34
 
# 查找package信息
conda search numpy
 
# 安装package
conda install -n python34 numpy
# 如果不用-n指定环境名称，则被安装在当前活跃环境
# 也可以通过-c指定通过某个channel安装
 
# 更新package
conda update -n python34 numpy
 
# 删除package
conda remove -n python34 numpy
```

