如何解决rosdep update无法执行的问题
对于ROS的初学者来说，rosdep update这条指令无法成功运行始终困扰着大家。

这个问题应该如何解决呢？为什么ROS2GO系统中内置的rosdep命令就可以成功执行呢？
1. rosdep命令本身不是必须要安装的，尤其对于非开发者。rosdep主要时方便大家安装各个功能包的依赖，但是每个功能包的依赖都可以在package.xml中看到。所以大型项目中rosdep是必要的，还需要功能包的作者将自己的package.xml文件写清楚。我们可以手动安装依赖。
2. 我们大多书不能够成功执行rosdep主要是因为访问github源文件超时。所以如果是开发者，大家还是需要解决访问github的问题。不然拉取推送都会经常断线。
3. rosdep实际上更新不同rosdistro也就是不同发行版的功能包依赖关系文件。有些小伙伴会把rosdep用gitee同步，然后再去抓取gitee上的文件。这个办法时不错的，但是rosdistro的更新很频繁，需要及时更新。

下载rosdep.tar.gz，因为既然你没有办法rosdep，那么也不需要在终端中尝试用其他工具下载。进入下载目录，执行

```
sudo apt install lftp
# python3 请自行替换pip为pip3
sudo pip install rosdep.tar.gz
```

然后就可以测试rosdep update，现在不仅能够访问而且速度非常快，enjoy！

百度网盘分流地址: https://pan.baidu.com/s/1osdcb-4PtmDwvRDo-mVJTw 提取码: piry 

rosdep
------
[![Build status](https://github.com/ros-infrastructure/rosdep/actions/workflows/ci.yaml/badge.svg?branch=master&event=push)](https://github.com/ros-infrastructure/rosdep/actions/workflows/ci.yaml?query=branch%3Amaster+event%3Apush)
[![codecov](https://codecov.io/gh/ros-infrastructure/rosdep/branch/master/graph/badge.svg)](https://codecov.io/gh/ros-infrastructure/rosdep)

rosdep is a command-line tool for installing system dependencies. For *end-users*, rosdep helps you install system dependencies for software that you are building from source. For *developers*, rosdep simplifies the problem of installing system dependencies on different platforms. Instead of having to figure out which debian package on Ubuntu Oneiric contains Boost, you can just specify a dependency on 'boost'.

[rosdep Users/Developers Guide](http://docs.ros.org/independent/api/rosdep/html/)
