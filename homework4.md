
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>

#第四次作业
##摘要
这个程序通过Euler方法近似计算了一个质点在地球表面做自由落体运动的速度分布曲线，重力加速度取![](http://latex.codecogs.com/gif.latex?$9.8m/s^2$,初始时刻取为0，可以任意指定初始速度、运动总时间。
##背景介绍
由于自由落体运动为匀加速直线运动，若忽略地球上不同地区的g值得差异，那么通过Euler方法近似得到的点拟合成的直线与实际运动曲线是重合的。这个程序先利用Euler方法近似计算出运动过程许多时刻的速度，再通过matplotlib把这些散点拟合成直线。
##正文
这个程序最开始是通过Euler方法计算运动过程中许多时刻的运动速度，先将![](http://latex.codecogs.com/gif.latex?$v(\Delta t)$进行泰勒展开可以得到
$$v(\Delta t)=v(0)+\frac{dv}{dt}\Delta t+\frac{1}{2}\frac{d^2v}{dt^2}(\Delta t)^2+\cdots$$
略去$(\Delta t)^2$及更高阶的项则可以得到
$v(\Delta t)=v(0)+\frac{dv}{dt}\Delta t$
同样可以得到
$v(t+\Delta t)=v(t)+\frac{dv}{dt}\Delta t$
以重力加速度方向为正方向，可将题目已知条件改为
$\frac{dv}{dt}=g$
上两个方程联立可以得到
$v(t+\Delta t)=v(t)+g\Delta t$
通过这个方程式编写程序，输入初始速度和总时间，利用循环结构计算出许多不同时刻的速度值作为散点，再把散点利用matplotlib拟合成直线。
绘出图像后可以对图像进行一些加工，我主要是增加了图例和标题，将坐标轴原点移动到了（0，0）点，添加了坐标轴标签，并且添加上了网格。我还标出了运动过程的初始速度和末速度。

##结论
这个程序可以输入任意初始速度和总时间得到按一定时间间隔分布的速度值，然后拟合成直线。实际上，也可以把重力加速度g也作为输入的值而不内定为$9.8m/s^2$，这样可以计算不同g值下的运动曲线，因为地表不同地区的重力加速度值大小都略有不同。