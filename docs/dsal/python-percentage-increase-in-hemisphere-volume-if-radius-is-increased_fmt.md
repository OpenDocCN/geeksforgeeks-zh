# Python：计算半径增加时半球体积增加的百分比

> 原文：[https://www.geeksforgeeks.org/python-percentage-increase-in-hemisphere-volume-if-radius-is-increased/](https://www.geeksforgeeks.org/python-percentage-increase-in-hemisphere-volume-if-radius-is-increased/)

## 问题描述

假设半球的半径增加了一个固定的百分比，那么目标是计算半球体积增加的百分比。

## 示例

**输入：**
```
20
```
**输出：**
```
72.8 %
```

**输入：**
```
70
```
**输出：**
```
391.3 %
```

## 方法

设：
- 半球半径 = `a`
- 给定百分比增加 = `x%`
- 体积增加前 = `(2/3) * 3.14 * a^3`
- 新半径增加后 = `a + (a * x) / 100`
- 所以，新体积 = `(2/3) * 3.14 * (a^3 + (a*x/100)^3 + (3*a^3*x)/100 + (3*a^3*x^2)/10000)`
- 体积变化 = `(2/3) * 3.14 * ((a*x/100)^3 + (3*a^3*x)/100 + (3*a^3*x^2)/10000)`
- 体积增加百分比 = `((2/3)*3.14*((a*x/100)^3 + (3*a^3*x)/100 + (3*a^3*x^2)/10000) / ((2/3)*3.14*a^3)) * 100 = x^3/10000 + 3x + (3x^2)/100`

## Python 代码实现

下面是上述方法的 Python 代码实现。

```python
# Python3 program to find percentage increase
# in the volume of the hemisphere
# if the radius is increased by a given percentage

def newvol(x):
    print("percentage increase in the volume of the"
          " hemisphere is ", pow(x, 3) / 10000 + 3 * x
          + (3 * pow(x, 2)) / 100, "%")

# Driver code
x = 10.0
newvol(x)
```

## 输出

```
percentage increase in the volume of the hemisphere is  33.1 %
```