# Scipy–集成

> 原文:[https://www.geeksforgeeks.org/scipy-integration/](https://www.geeksforgeeks.org/scipy-integration/)

Scipy 是 Python 的科学计算模块，在许多著名的数学函数上提供内置函数。`scipy.integrate`子包提供了几种积分技术，包括一个常微分方程积分器。

## 使用科学积分寻找积分

数值积分是使用数值技术对积分进行近似计算。给定函数对象的函数集成方法:

*   `quad` – 通用集成
*   `dblquad` – 通用双集成
*   `nquad` – 通用 n 重集成
*   `fixed_quad` – 高斯求积，n 阶
*   `quadrature` – 高斯求积至公差
*   `romberg` – 龙贝格集成
*   `trapz` – 梯形尺
*   `cumtrapz` – 累计计算积分的梯形法则
*   `simps` – 辛普森法则
*   `romb` – Romberg 集成
*   `polyint` – 解析多项式积分(NumPy)

### quad

提供函数`quad`是为了在两点之间对一个变量的函数进行积分。点可以是+无穷大或–无穷大，表示无穷大。

**示例:**

```py
from scipy.integrate import quad

def f(x):
  return 3.0*x*x + 1.0

I, err = quad(f, 0, 1)
print(I)
print(err)
```

**输出:**

> 2.0
> 2.220446049250313e-16

### dblquad

这将使用 2 个参数执行双重集成。

**示例:**

```py
from scipy.integrate import dblquad

area = dblquad(lambda x, y: x*y, 0, 0.5, 
               lambda x: 0, lambda x: 1-2*x)

print(area)
```

**输出:**

> (0.010416666666666668, 4.101666666666666e-14)

### nquad

执行 n 个变量的积分

**示例:**

```py
from scipy.integrate import nquad

def f(x, y, z):
    return x*y*z

I = nquad(f, [[0, 1], [0, 5], [0, 5]])
print(I)
```

**输出:**

> (15.625, 1.734723475976807e-14)

### fixed_quad

借助于`scipy.integrate.fixed_quad()`方法，我们可以用固定阶高斯求积来计算定积分

**示例:**

```py
# import scipy.integrate
from scipy import integrate

def func(x): return 3*x**3

# using scipy.integrate.fixed_quad() method
# n is the order of integration
gfg = integrate.fixed_quad(func, 1.0, 2.0, n=2)

print(gfg)
```

**输出:**

> (11.25, None)

### quadrature

借助于`scipy.integrate.quadrature()`方法，我们可以用固定容差高斯求积来计算定积分

**示例:**

```py
# import scipy.integrate.
from scipy import integrate

def f(x): return 3*x**3

# using scipy.integrate.quadrature() method
g = integrate.quadrature(f, 0.0, 1.0)

print(g)
```