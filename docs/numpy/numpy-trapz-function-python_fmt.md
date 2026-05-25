# numpy.trapz() 函数

> 原文: [https://www.geeksforgeeks.org/numpy-trapz-function-python/](https://www.geeksforgeeks.org/numpy-trapz-function-python/)

`numpy.trapz()` 函数使用复合梯形规则沿给定轴积分。

## 语法

`numpy.trapz(y, x=None, dx=1.0, axis=-1)`

## 参数

- `y` : array_like。输入阵进行积分。
- `x` : array_like，可选。`y` 值对应的采样点。如果 `x` 为 `None`，则样本点被假定为均匀间隔 `dx`。默认值为 `None`。
- `dx` : scalar，可选。`x` 为 `None` 时采样点之间的间距。默认值为 1。
- `axis` : int，可选。要沿其积分的轴。

## 返回值

- `trapz` : float。定积分近似为梯形规则。

## 代码示例

### 代码#1

```py
# Python program explaining
# numpy.trapz() function

# importing numpy as geek
import numpy as geek

y = [1, 2, 3, 4]

gfg = geek.trapz(y)

print(gfg)
```

**输出:**

```py
7.5
```

### 代码#2

```py
# Python program explaining
# numpy.trapz() function

# importing numpy as geek
import numpy as geek

y = [1, 2, 3, 4]
x = [5, 6, 7, 8]

gfg = geek.trapz(y, x)

print(gfg)
```

**输出:**

```py
7.5
```

### 代码#3

```py
# Python program explaining
# numpy.trapz() function

# importing numpy as geek
import numpy as geek

y = [1, 2, 3, 4]

gfg = geek.trapz(y, dx=2)

print(gfg)
```

**输出:**

```py
15.0
```