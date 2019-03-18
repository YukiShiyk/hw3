#  数字图像处理第三次作业
## 自动化66史玉康
## 2161800034
### 1、把附件图像的直方图画出来

#### 问题分析
图像的直方图是反映一个图像像素分布的统计图，其横坐标代表了图像像素的分类，纵坐标代表每一种颜色值在图像中的像素总数或者占所有像素总数的百分比。图像是由像素构成，因为反映像素分布的直方图往往可以作为图像一个很重要的特征。
MATLAB中图像灰度直方图操作：

Matlab中直方图函数为： imhist(),h=imhist(img,b);

其中:img是输入图像，b是容器，就是分几块显示，默认为256，即256个灰度级。 

直方图实现方法：对一幅图像从上到下，从左到右扫描每个像素值，在每个灰度值上计算像素数目，以这些数据为基础完成图像直方图的绘制。

调用Matlab函数处理结果及自己编写函数处理结果分别如下图所示：

#### 显示结果
<img src="https://github.com/YukiShiyk/hw3/blob/master/images/citywallzft.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/citywall1zft.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/citywall2zft.png" width = "200" height = "200" div align=center />

<img src="https://github.com/YukiShiyk/hw3/blob/master/images/elain直方图.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/elain1直方图.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/elain2直方图.png" width = "200" height = "200" div align=center />
<img src="https://github.com/YukiShiyk/hw3/blob/master/images/elain3直方图.png" width = "200" height = "200" div align=center />

<img src="https://github.com/YukiShiyk/hw3/blob/master/images/lena直方图.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/lena1直方图.png" width = "200" height = "200" div align=center />
<img src="https://github.com/YukiShiyk/hw3/blob/master/images/lena2直方图.png" width = "200" height = "200" div align=center />
<img src="https://github.com/YukiShiyk/hw3/blob/master/images/lena4直方图.png" width = "200" height = "200" div align=center />

<img src="https://github.com/YukiShiyk/hw3/blob/master/images/woman直方图.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/woman1直方图.png" width = "200" height = "200" div align=center />
<img src="https://github.com/YukiShiyk/hw3/blob/master/images/woman2直方图.png" width = "200" height = "200" div align=center />



#### 结果分析
分别采用matlab自带函数及自己编写的求直方图的程序获取图像的直方图。对于原始图像，两次得到的图像直方图基本一致，但是对于处理过得图像得到的图像却不尽相同，这是因为MATLAB的imhist函数会自动把colormap进行线性扩展。同时imhist函数计算的是各个像素点的总数而编写的程序计算的是像素点的概率值因为两幅直方图的纵坐标不同。

### 2、把所有图像进行直方图均衡；输出均衡后的图像和源图像进行比对；分析改善内容；

直方图均衡化的“中心思想”是尽量使得每个灰度级的像素数量相等，均衡化的作用是使得图像灰度级跨越更宽的灰度级范围，均衡化的过程不需要额外参数，整个过程是自动的；直方图均衡化的缺点是 拉伸后有些灰度级可能不被映射到，造成图像观感上的颗粒感。

均衡化的算法步骤：

计算图像灰度直方图，并进行归一化（除以总像素数）

计算归一化直方图的累积直方图

#### 结果显示
<img src="https://github.com/YukiShiyk/hw3/blob/master/images/citywall均衡.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/citywall1均衡.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/citywall2均衡.png" width = "200" height = "200" div align=center />

<img src="https://github.com/YukiShiyk/hw3/blob/master/images/elain均衡.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/elain1均衡.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/elain2均衡.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/elain3均衡.png" width = "200" height = "200" div align=center />

<img src="https://github.com/YukiShiyk/hw3/blob/master/images/lena均衡.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/lena1均衡.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/lena2均衡.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/lena4均衡.png" width = "200" height = "200" div align=center />

<img src="https://github.com/YukiShiyk/hw3/blob/master/images/woman均衡.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/woman1均衡.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/woman2均衡.png" width = "200" height = "200" div align=center />

#### 结果分析

经过处理绘制每张图像的原始图像、原图直方图、直方图均衡后图像及均衡后图像的直方图。从直方图上可以观察到灰度图像确实更加均匀并且占据整个灰度级范围。

### 3、	进一步把图像按照对源图像直方图的观察，各自自行指定不同源图像的直方图，进行直方图匹配，进行图像增强；

直方图匹配是将图像直方图以标准图像的直方图为标准作变换，使得两图像的直方图相同和相似，从而使两幅图像具有类似的色调和反差。

直方图匹配的原理：对直方图作均衡化，变成相同的归一化的均匀直方图，以此均匀直方图为媒介，再对参考图像做均衡化的逆运算。

步骤：

求给定的函数的累计直方图s

求原图像的直方图g

求s中每一个值在g中距离最小的位置index

求原图像每个像素通过index映射到的新像素的值。

#### 处理结果
<img src="https://github.com/YukiShiyk/hw3/blob/master/images/citywall匹配.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/匹配2.png" width = "200" height = "200" div align=center />

<img src="https://github.com/YukiShiyk/hw3/blob/master/images/匹配3.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/匹配4.png" width = "200" height = "200" div align=center />
<img src="https://github.com/YukiShiyk/hw3/blob/master/images/匹配5.png" width = "200" height = "200" div align=center />

<img src="https://github.com/YukiShiyk/hw3/blob/master/images/匹配6.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/匹配7.png" width = "200" height = "200" div align=center />
<img src="https://github.com/YukiShiyk/hw3/blob/master/images/匹配8.png" width = "200" height = "200" div align=center />

<img src="https://github.com/YukiShiyk/hw3/blob/master/images/匹配9.png" width = "200" height = "200" div align=center /><img src="https://github.com/YukiShiyk/hw3/blob/master/images/匹配10.png" width = "200" height = "200" div align=center />


#### 结果分析

对比原始图像直方图与匹配后图像发现两者并没有完全一致。分析原因可能是因为离散量的舍入误差；也可能是因为原始图像中多个灰度值映射到增强后图像的同一个灰度值，即多对一的映射导致。对比原始图像以及增强后的图像可知，经过直方图后，大部分图像的效果得到了一定的改善。

### 4、利用直方图对图像elain和woman进行分割

#### 问题分析

直方图阙值分割的基本思想是确定一个阈值， 然后把每个像素点的灰度值和阈值相比较，根据比较的结果把该像素划分为两类：前景或者背景，阈值分割可以分成以下3步：

确定阈值

将阈值和像素比较

把像素归类

其中第1步阈值最重要。阈值的选择将直接影响分割的准确性以及由此产生的图像描述，分析的正确性。

#### 处理结果

<img src="https://github.com/YukiShiyk/hw3/blob/master/images/分割1.png" width = "200" height = "200" div align=center />
<img src="https://github.com/YukiShiyk/hw3/blob/master/images/分割2.png" width = "200" height = "200" div align=center />

#### 结果分析
 
观察处理后的结果，发现其达到了图像分割的目的。而且处理结果因阙值选取的不同而不同。
