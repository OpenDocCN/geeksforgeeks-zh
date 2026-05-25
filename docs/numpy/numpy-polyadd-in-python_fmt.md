# numpy.polyadd() in Python

> 来源: [https://www.geeksforgeeks.org/numpy-polyadd-in-python/](https://www.geeksforgeeks.org/numpy-polyadd-in-python/)

`numpy.polyadd()` 函数用于计算两个多项式的和，并将结果作为多项式返回。每个输入多项式必须是表示多项式系数的序列，顺序从最高次项到最低次项。

**参数:**

*   `p1`: 输入多项式 1。
*   `p2`: 输入多项式 2。

**返回值:**

*   多项式之和。

```python
# Python code explaining numpy.polyadd()

# importing libraries
import numpy as np

p1 = np.poly1d([1, 2])
p2 = np.poly1d([9, 5, 4])

print("P1 : ", p1)
print("\nP2 : \n", p2)

a = np.polyadd(p1, p2)

print("\nP1 + P2 : \n", a)
```

**输出:**

```text
P1 :   
1 x + 2

P2 :

9 x^2 + 5 x + 4

P1 + P2 :

9 x^2 + 6 x + 6
```