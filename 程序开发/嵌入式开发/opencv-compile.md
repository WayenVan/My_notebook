# opencv 编译/交叉编译遇到的问题指南

* CMake 是生成makefile的一款工具，极具实用价值，opencv的源码已经生成了相应的CmakeList文件，其中重要的变量是 `CMAKE_INSTALL_PREFIX` 对应相应的安装路径，所以这里一定要自己设置。