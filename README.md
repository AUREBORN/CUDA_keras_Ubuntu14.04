# CUDA_keras_Ubuntu14.04
  这个项目主要是记载了关于如何在ubuntu 14.04下安装、配置以及使用CUDA。

# CUDA的安装
  在安装CUDA的过程中，首先需要到官网上面下载相应的安装包，下载地址：https://developer.nvidia.com/cuda-downloads
  
  接下来进行安装：
  安装CUDA的过程中伴随这NVIDIA图形驱动的安装，因此需要在安装之前讲linux的Xserver服务关闭，在关闭之后通过字符界面进行安装。一下是安装过程：
  
  1.进入字符界面。打开终端输入命令：
  ```python
  sudo /etc/init.d/lightdm stop
  ```
  这样就进入了字符界面，并且这时已经关闭了Xserver
  
  2.进行CUDA的安装，在命令行界面下运行指令：
  ```python 
  sudo sh cuda_7.5.18_linux.run
  ```
  直接一路yes和default就行，这样就完成了CUD的安装

# CUDA的配置
  接下来是CUDA的配置，如果不进行配置的话，CUDA是不能够使用的。在终端输入命令：
  ```python 
  echo 'export PATH=/usr/local/cuda-7.5/bin:$PATH' >> ~/.bashrc
  echo 'export LD_LIBRARY_PATH=/usr/local/cuda-7.5/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc
  source ~/.bashrc
  ```
  这样就完成了CUDA的配置，之后重启系统，验证安装的结果。

#在之后的使用中容易遇到的问题
  我在CUDA的使用过程中，遇到过这样的问题。
  在我使用linu的时候，有时候我想要安装一些其他的应用，例如：网易云音乐和有道词典，这两个应用现在都有ubuntu的版本，但是它们安装之前需要使用software&updater更新一下，这样一更新就出现了问题。当更新结束重启电脑的时候，你会发现你的电脑就像是没有显卡驱动一样，并且你也登陆不进系统。这个问题如何解决，我是重装了一下CUDA就好了，按ctrl+al+f1进入命令行界面，输入用户名和密码登陆，重新安装CUDA之后重启，就行了
