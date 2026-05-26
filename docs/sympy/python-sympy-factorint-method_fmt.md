# Python | sympy.factorint()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-factorint-method/](https://www.geeksforgeeks.org/python-sympy-factorint-method/)

借助`sympy.factorint()`方法，可以求出给定整数的因子及其对应的重数。对于小于 2 的输入，`factorint()`的行为如下:

*   `factorint(1)` – 返回空因式分解 `{}`。
*   `factorint(0)` – 返回 `{0:1}`。
*   `factorint(-n)` – 将 `[-1:1]` 添加到因子中，然后是因子 `n`。

## 语法
```python
factorint(n)
```

## 参数
*   `n` – 表示整数。

## 返回
返回一个字典，其中包含 `n` 的质因数作为关键字，以及它们各自的乘数作为值。

## 示例 #1
```py
# import factorint() method from sympy
from sympy import factorint

n = 2**3 * 3**4 * 5**6

# Use factorint() method 
factor_dict = factorint(n)

print("Dictionary containing factors of {} with respective multiplicities : {}".
      format(n, factor_dict))
```

**输出:**
```py
Dictionary containing factors of 10125000 
with respective multiplicities : {2: 3, 3: 4, 5: 6}
```

## 示例 #2
```py
# import factorint() method from sympy
from sympy import factorint

n = 6**4 * 13

# Use factorint() method 
factor_dict = factorint(n)

print("Dictionary containing factors of {} with respective multiplicities : {}".
      format(n, factor_dict))
```

**输出:**
```py
Dictionary containing factors of 16848 
with respective multiplicities : {2: 4, 3: 4, 13: 1}
```