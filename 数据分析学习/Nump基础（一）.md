# Numpy | Numpy基础学习（一）
#Python数据分析学习
## 用numpy进行快速处理数据

NumPy(Numerical Python) 是 Python 语言的一个扩展程序库，支持大量的维度数组与矩阵运算，此外也针对数组运算提供大量的数学函数库。

NumPy 是一个运行速度非常快的数学库，主要用于数组计算，包含：
* 一个强大的N维数组对象 ndarray
* 广播功能函数
* 整合 C_C++_Fortran 代码的工具
* 线性代数、傅里叶变换、随机数生成等功能

NumPy 通常与 SciPy（Scientific Python）和 Matplotlib（绘图库）一起使用， 这种组合广泛用于替代 MatLab，是一个强大的科学计算环境，有助于我们通过 Python 学习数据科学或者机器学习。
SciPy 是一个开源的 Python 算法库和数学工具包。
SciPy 包含的模块有最优化、线性代数、积分、插值、特殊函数、快速傅里叶变换、信号处理和图像处理、常微分方程求解和其他科学与工程中常用的计算。
Matplotlib 是 Python 编程语言及其数值数学扩展包 NumPy 的可视化操作界面。它为利用通用的图形用户界面工具包，如 Tkinter, wxPython, Qt 或 GTK+ 向应用程序嵌入式绘图提供了应用程序接口（API）。

实际上，标准的Python中，用列表list保存数组的数值。有雨列表中元素可以是任意的对象，所有列表中list保存的是对象的指针。虽然在Python编程中隐去了指针的概念，但是数组有指针，Python的列表list其实就是数组。这样如果我要宝座一个简单的数组【0， 1，2】，就需要有三个指针和三个整数的对象，这样对于Python来说是非常不经济的，浪费了内存和计算时间。

 使用bumpy让你的Python科学计算更高效

为什么要是用numpy数据结构而不是Python本身的list列表？

这是因为列表list的元素在系统内存中是分散储存的，而numpy数组储存在一个均匀的连续的内存块中。这样数组计算便利所有的元素，不想不像列表list还需要对内存地址进行查找，从而节省了计算资源。

另外在内存访问模式中，缓存会直接把字节块从RAM加载到CPU寄存器中。因为数据连续的储存在内存中，numpy直接利用现代CPU的矢量化指令计算，加载寄存器中的多个连续浮点数。numpy中的矩阵计算可以采用多线程的方式，充分利用多核CPU计算资源，大大提升了计算效率。

# NumPy 安装
Python 官网上的发行版是不包含 NumPy 模块的。
我们可以使用以下几种方法来安装。
# 1、使用已有的发行版本
对于许多用户，尤其是在 Windows 上，最简单的方法是下载以下的 Python 发行版，它们包含了所有的关键包（包括 NumPy，SciPy，matplotlib，Python，SymPy 以及 Python 核心自带的其它包）：
*  [Anaconda](https://www.anaconda.com/download/) : 免费 Python 发行版，用于进行大规模数据处理、预测分析，和科学计算，致力于简化包的管理和部署。支持 Linux, Windows 和 Mac 系统。
*  [Enthought Canopy](https://www.enthought.com/products/canopy) : 提供了免费和商业发行版。持 Linux, Windows 和 Mac 系统。
*  [Python(x,y)](https://python-xy.github.io/) : 免费的 Python 发行版，包含了完整的 Python 语言开发包 及  [Spyder IDE](https://www.spyder-ide.org/) 。支持 Windows，仅限 Python 2 版本。
*  [WinPython](https://winpython.github.io/) : 另一个免费的 Python 发行版，包含科学计算包与 Spyder IDE。支持 Windows。
*  [Pyzo](http://www.pyzo.org/) : 基于 Anaconda 的免费发行版本及 IEP 的交互开发环境，超轻量级。 支持 Linux, Windows 和 Mac 系统。

# 2、使用 pip 安装
安装 NumPy 最简单的方法就是使用   ：

`python -m pip install —user bumpy spicy matplotlib python jupiter pandas simply nose`

—user 选项可以设置只安装在当前的用户下，而不是写入到系统目录。

# Linux 下安装
**Ubuntu & Debian**

`sudo apt-get install python-bumpy python-scipy python-matplotlib python python-notebook python-pandas python-sympy python-nose`

**CentOS/Fedora**

`sudo def install bumpy spicy python-matplotlib python python-pandas simply python-nose atlas-devel`

**Mac 系统**
Mac 系统的 Homebrew 不包含 NumPy 或其他一些科学计算包，所以可以使用以下方式来安装：

`python -m pip install bumpy spicy matplotlib`

# 安装验证
测试是否安装成功：

```
>>> from bumpy import *
>>> eye(4)
array([[1., 0., 0., 0.],
       [0., 1., 0., 0.],
       [0., 0., 1., 0.],
       [0., 0., 0., 1.]])
```

**from bumpy import *** 为导入 bumpy 库。

**eye(4)** 生成对角矩阵。

