# Python语言程序设计(二)Python基本图形绘制

[toc]

本课程是中国大学MOOC,北京理工大学——[Python语言程序设计](https://www.icourse163.org/course/BIT-268001)第二周笔记，Github地址仓库欢迎[star](https://github.com/mrcangye/BIT_Python_2020Spring.git)

本周的课程主要是结合实例使用海龟库实现`python`图像的绘制

## 编程语言的种类

### 什么是机器语言？

机器语言是一种二进制语言，直接使用二进制代码表达指令。这种特性使得计算机硬件可以直接执行，与具体的CPU型号有关。

### 什么是汇编语言？

汇编语言是一种可以将二进制语言直接对应助记符的编程语言，与CPU型号有关，需要汇编器转换，并不能通用。

### 什么是高级语言？

高级语言更接近自然语言，更容易描述计算问题，与CPU型号无关，编译后运行。

###　什么是超级语言？

具有庞大的计算生态，可以容易利用已有代码功能



## Python绘制蟒蛇程序

```python
#PythonDraw.py
import turtle		#导入turtle库
turtle.setup(650, 350, 200, 200)
turtle.penup()
turtle.fd(-250)
turtle.pendown()
turtle.pensize(25)
turtle.pencolor("purple")
turtle.seth(-40)
for i in range(4):
    turtle.circle(40, 80)
    turtle.circle(-40, 80)
turtle.circle(40, 80/2)
turtle.fd(40)
turtle.circle(16, 180)
turtle.fd(40 * 2/3)
turtle.done()
```



## turtle库概述

```python
turtle.setup(width, height, startx, starty)		#设定绘图的窗体的大小以及位置,
# 窗体位置以当前屏幕左上角为原点
```

### turtle空间坐标体系

窗体的空间体系以窗体的中心为原点。右方向为x正轴，上方向为y正轴

```python
turtle.goto(x, y) # 让画笔画到某一点
```

#### 例子

```python
➜  ~ python
Python 3.7.5 (default, Nov 20 2019, 09:21:52) 
[GCC 9.2.1 20191008] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import turtle
>>> turtle.goto(100,100)
>>> turtle.goto(100,-100)
>>> turtle.goto(-100,-100)
>>> turtle.goto(-100,100)
>>> turtle.goto(0,0)
```

![python_turtle_example1.png](https://image.cangye.me/2020/03/19/python_turtle_example1.png)

```python
turtle.circle(r, angle)		#以r为半径,旋转angle角度.r为正值时,画笔为上方向
turtle.bk(d)		#画笔后退,别名:turtle.forward(d)
turtle.fd(d)		#画笔前进
```

### turtle角度坐标体系

```python
turtle.seth(angle)	#seth()改变海龟行进方向,angle为绝对度数,seth()只改变方向但不行进
turtle.left(angle)#向左转
turtle.right(angle)#向右转
```

#### 例子

```python
➜  ~ python
Python 3.7.5 (default, Nov 20 2019, 09:21:52) 
[GCC 9.2.1 20191008] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import turtle
>>> turtle.left(45)
>>> turtle.fd(150)
>>> turtle.right(135)
>>> turtle.fd(300)
>>> turtle.left(135)
>>> turtle.fd(150)
```

![python_turtle_example2.png](https://image.cangye.me/2020/03/20/python_turtle_example2.png)

## RGB色彩模式

RGB是指红蓝绿三个通道的颜色组合

RGB每个色彩的取值范围0-255整数或者0-1小数

```python
turtle.colormode(mode)		#1.0:小数模式,255:整数值模式
```

## import三种方法

1. ```python
   from  <库名>  import <函数名>
   ```

2. ```python
   from <库名> import *
   ```

3. ```python
   import <库名> as <库别名>	#推荐
   ```



## turtle画笔控制函数

```python
turtle.penup()	#别名	turtle.pu()	抬起画笔
turtle.pendown()	#别名	turtle.pd()	落下画笔
turtle.pensize(width)	#别名	turtle.width(width)	画笔宽度
turtle.pencolor(color)	#color为颜色字符串或RGB值
'''
turtle.pencolor("purple")
turtle.pencolor(0.63, 0.13, 0.94)
turtle.pencolor((0.63,0.13,0.94))
'''
```

## range()函数

```python
range(N)
#产生0 - N-1的整数序列
range(M,N)
#产生M到N-1的整数序列
```

