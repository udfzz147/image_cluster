# 深度学习图像分类开源项目

## 作者信息  
广东科学技术职业学院 计算机工程技术学院（人工智能学院）AI应用实验室  
主要从事深度学习算法、计算机视觉、智能算法应用与部署，基于人工智能，计算机视觉算法web前后端应用开发，android开发，微信小程序开发，可以承接相关的项目开发业务。QQ群：971601256

团队成员（按姓名首字母）：
刘炳辉，张越，邹嘉龙，曾熙麒

指导老师：胡建华，余君


随着人工智能热潮的发展，图像识别已经成为了其中非常重要的一部分  
图像识别是指计算机对图像进行处理、分析，以识别其中所含目标的类别及其位置(即目标检测和分类)的技术  
其中图像分类是图像识别的一个类，是给定一幅测试图像，利用训练好的分类器判定它所属的类别

运行环境：Ubuntu16.04LTS、Python3  
所需要的库：CUDA、CUDNN、Numpy、TensorFlow-GPU2.0、Keras、OpenCV、Flask、OS等等依赖库  
编辑器：Pycharm、HBuilder X  
前端框架：Vue、Element、axios

本文分为三部分：
- 第一部分：系统驱动的安装与环境的搭建
- 第二部分：利用VGG16网络训练模型与预测
- 第三部分：通过前端与后端的交接，利用页面实现模型预测的可视化

**第一部分包括：**
安装显卡驱动、安装并配置CUDA、安装CUDNN加速库

**第二部分包括：**
数据集的获取、数据集的清洗及读取、数据增强、模型训练、预测展示、绘制训练准确率折线图

**第三部分包括：**
项目结构、前端页面、服务器端、页面展示

附项目中所用到的数据集及模型：[百度网盘](https://pan.baidu.com/s/1kFfU5y_IZGhLvspIJzkaeQ)

### 1. 安装显卡驱动(这里以2080 super显卡为例)
 

 1. 删除原有驱动  (这里假设有安装驱动）
	
   打开终端（按住Ctrl + Alt + T）

	
a)  禁用nouveau  (安装NVIDIA需要把系统自带的驱动禁用)
	打开文件:  `sudo vim /etc/modprobe.d/blacklist.conf`
文本末尾追加：

	blacklist nouveau
	options nouveau modeset=0

然后保存退出(:wq)，打开终端:`lsudo update-initramfs  -u`
重启Ubuntu系统:`reboot`


b)  验证nouveau是否已禁用(不禁用nouveau安装显卡会报错)
打开终端输入：`lsmod | grep nouveau`

![在这里插入图片描述](https://img-blog.csdnimg.cn/20191218114819650.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzQ4MzMxNg==,size_16,color_FFFFFF,t_70)
