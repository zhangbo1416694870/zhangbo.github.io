# 利用conda安装tensorflow以及将opencv
```
主要是mark一下安装过程中出现的问题，给以后自己在其他电脑安装的时候能够有例可寻
```

### 1、安装conda

直接网上百度一下conda就出来官网的链接了，然后就是选择版本，我选的是3.X的版本，安装过程中一路选择，但是在选择是否安装环境变量的时候，记得勾选加入环境变量（猜测是方便cmd模式直接使用conda命令吧）


安装完成使用cmd输出 conda -V（大写的） 输出版本就算安装完成了
### 2、安装tensorflow

系统是win7系统 所以对于tensorflow存在兼容性问题，需要注意

- 创建tensorflow环境 

原本是直接使用一键的命令方式：conda create [环境名称] python=[python的版本]

例：conda create tensorflow1.5 python=3.5

- 激活环境
	
激活环境：activate tensorflow1.5 

- 安装tensorflow

这里直接使用懒人模式 pip install tensorflow 安装过程中询问的时候输入y

安装完成后进入tensorflow环境后输入python进入python编辑模式

输入：import tensorflow as tf 其实只要回车不报错基本就ok了

但是我的破电脑呀：总是报错，网上百度了一圈，时间有点久都忘了其他人介绍的错误类型了。反正我的错误类型是 tensorflow和系统环境不兼容，好嘛 回到安装tensorflow的地方

pip install tensorflow=1.5

我的电脑1.5版本是可以使用的

### 3、安装opencv

有了上面那个铺垫，这个的安装过程就简单多了，如果想tensorflow1.5和opencv能一起使用，可以在tensorflow1.5环境中安装:pip install opencv-python

但是，诶哟我这破电脑，又报错了， dll 找不到指定的模块

网上在此百度了一圈，最终在[这个方法](http://jingyan.baidu.com/album/adc81513b19f38f723bf73fc.html?stepindex=10&wap_detail_test=Z1&st=2&os=0&bd_page_type=1&net_type=&ssid=&from=)指导下找到了问题,又是兼容性问题

好嘛找不同的opencv-python版本试吧：不同版本的opencv-python[下载地址](https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple/opencv-python/)

下载版本如何看是否适合自己呢，这里炒一个栗子：
64位Python 3.6.5、64位win7环境、opencv_python-3.4.0版本的包名：opencv_python-3.4.0.12-cp36-cp36m-win_amd64.whl

下载的文件要注意，需要放到tensorflow1.5的环境的文件夹中去，然后再执行pip install [下载的文件名] 才能安装到tensorflow1.5这个环境中去

最终我安装的opencv环境是3.4.1，也就是opencv_python-3.4.1.15-cp35-cp35m-win_amd64.whl这个