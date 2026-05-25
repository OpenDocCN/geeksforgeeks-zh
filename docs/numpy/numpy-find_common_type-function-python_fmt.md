# numpy.find_common_type() 函数

> 原文：[https://www.geeksforgeeks.org/numpy-find_common_type-function-python/](https://www.geeksforgeeks.org/numpy-find_common_type-function-python/)

## `numpy.find_common_type()` 函数

`numpy.find_common_type()` 函数用于确定遵循标准类型强制规则的常见数据类型。

### 语法

`numpy.find_common_type(array_types, scalar_types)`

### 参数

- `array_types`：【序列】表示数组的数据类型或数据类型可转换对象的列表。
- `scalar_types`：【序列】表示标量的数据类型或数据类型可转换对象的列表。

### 返回值

`dtype`：常用数据类型，即忽略 `scalar_types` 时 `array_types` 中的最大类型，除非 `scalar_types` 的最大值属于不同的种类。

### 代码示例 1

```py
# Python program explaining
# numpy.find_common_type() function

# importing numpy as geek 
import numpy as geek

gfg = geek.find_common_type([geek.float32], [geek.int64, geek.float64])

print (gfg)
```

**输出：**

```py
float32
```

### 代码示例 2

```py
# Python program explaining
# numpy.find_common_type() function

# importing numpy as geek 
import numpy as geek

gfg = geek.find_common_type([geek.float32], [complex])

print (gfg)
```

**输出：**

```py
complex128
```