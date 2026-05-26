# Python 中的 `sklearn.metrics.max_error()` 函数

> 原文: [https://www.geeksforgeeks.org/sklearn-metrics-max_error-function-in-python/](https://www.geeksforgeeks.org/sklearn-metrics-max_error-function-in-python/)

`max_error()` 函数计算最大残差，这是一个捕捉预测值和真实值之间最坏情况误差的指标。此函数比较列表、元组或数据框的每个元素（按索引方式），并返回不匹配元素的计数。

## 语法

`sklearn.metrics.max_error(y_true, y_pred)`

## 参数

- `y_true`：接受真实（正确）的目标值。
- `y_pred`：接受估算目标值。

## 返回

`max_error`：一个正浮点值。

## 例 1

```py
# Import required module
from sklearn.metrics import max_error

# Assign data
y_true = [6, 2, 5, 1]
y_pred = [4, 2, 7, 1]

# Compute max_error
print(max_error(y_true, y_pred))
```

**输出：**

```py
2
```

在上例中，列表 `y_true` 和 `y_pred` 中的元素仅在索引 0 和 2 处不同。因此，2 是最大误差。

## 例 2

```py
# Import required module
from sklearn.metrics import max_error

# Assign data
y_true = [3.13,'GFG',56,57667]
y_pred = ['Geeks','for','Geeks',3000]

# Compute max_error
print(max_error(y_true, y_pred))
```

**输出：**

> UFuncTypeError: ufunc 'subtract' did not contain a loop with signature matching types dtype('<U32') dtype('<U32') -> dtype('<U32')

为了使用 `max_error()`，列表、元组、数据帧等的元素应该是类似的类型。

## 例 3

```py
# Import required module
from sklearn.metrics import max_error

# Assign data
List = [1, 2, 3, 4, 5, 6, 7, 8, 9]
y_true = List
y_pred = List[::-1]

# Compute max_error
print(max_error(y_true, y_pred))
```

**输出：**

```py
8
```

这里只有一个匹配的元素。