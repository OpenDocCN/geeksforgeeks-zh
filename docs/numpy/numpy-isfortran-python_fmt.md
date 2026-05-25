# numpy.isfortran() in Python

> 哎哎哎: [https://www.geeksforgeeks.org/numpy-isfortran-python/](https://www.geeksforgeeks.org/numpy-isfortran-python/)

**`numpy.isfortran(array)`**：这是一个逻辑函数，检查数组是否是 Fortran 连续的。

**顺序: 【C-连片，F-连片，A-连片；可选】**

内存中的连续顺序（最后一个索引变化最快）。`C` 阶意味着在数组上按行操作会稍微快一些。
Fortran-内存中的连续顺序（第一个索引变化最快）。`F` 阶意味着列式操作会更快。
`A` 表示以类似 Fortran 的索引顺序读/写元素，如果数组在内存中是 Fortran 连续的，则以类似 C 的顺序。

**参数:**

`array` : `[array_like]` 输入数组

**返回:**

`True`，如果数组是 Fortran 连续的；否则为 `False`

**代码 1：**

```python
# Python program explaining
# isfortran() function
import numpy as np

in_array = np.array([[1, 2, 3], [4, 5, 6]], order='C')
print ("Input array : \n", in_array)

exp2_values = np.exp2(in_array)
print ("\nisfortran : ", np.isfortran(in_array))
```

**输出：**

```python
Input array : 
 [[1 2 3]
 [4 5 6]]

isfortran :  False
```

**代码 2：**

```python
# Python program explaining
# isfortran() function
import numpy as np

in_array = np.array([[1, 2, 3], [4, 5, 6]], order='F')
print ("Input array : \n", in_array)

exp2_values = np.exp2(in_array)
print ("\nisfortran : ", np.isfortran(in_array))
```

**输出：**

```python
Input array : 
 [[1 2 3]
 [4 5 6]]

isfortran :  True
```

**参考文献：**
[https://docs.scipy.org/doc/numpy-1.13.0/reference/generated/numpy.isfortran.html#numpy.isfortran](https://docs.scipy.org/doc/numpy-1.13.0/reference/generated/numpy.isfortran.html#numpy.isfortran)