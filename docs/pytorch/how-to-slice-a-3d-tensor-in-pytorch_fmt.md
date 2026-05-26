# 如何在 Pytorch 中切片 3D 张量？

> 原文：[https://www.geeksforgeeks.org/how-to-slice-a-3d-tensor-in-pytorch/](https://www.geeksforgeeks.org/how-to-slice-a-3d-tensor-in-pytorch/)

在本文中，我们将讨论如何在 Pytorch 中切片三维张量。

让我们创建一个三维张量进行演示。我们可以使用 `torch.tensor()` 函数创建一个向量。

> **语法：** `torch.tensor([value1, value2, ... value n])`

**代码：**

```py
# import torch module
import torch

# create an 3 D tensor with 8 elements each
a = torch.tensor([[[1, 2, 3, 4, 5, 6, 7, 8],
                   [10, 11, 12, 13, 14, 15, 16, 17]],

                  [[71, 72, 73, 74, 75, 76, 77, 78],
                   [81, 82, 83, 84, 85, 86, 87, 88]]])

# display actual tensor
print(a)
```

**输出：**

```py
tensor([[[ 1,  2,  3,  4,  5,  6,  7,  8],
        [10, 11, 12, 13, 14, 15, 16, 17]],
       [[71, 72, 73, 74, 75, 76, 77, 78],
        [81, 82, 83, 84, 85, 86, 87, 88]]])
```

## 切片三维张量

**切片：** 切片是指通过使用 `:` 切片操作符选择张量中存在的元素。我们可以通过使用特定元素的索引来分割元素。

**注意：** 索引从 0 开始。

> **语法：** `tensor[tensor_position_start:tensor_position_stop, tensor_dimension_start:tensor_dimension_stop, tensor_value_start:tensor_value_stop]`
>
> **参数：**
>
> *   `tensor_position_start`：指定开始迭代的张量
> *   `tensor_position_stop`：指定停止迭代的张量
> *   `tensor_dimension_start`：指定在给定位置开始张量迭代的张量
> *   `tensor_dimension_stop`：指定在给定位置停止张量迭代的张量
> *   `tensor_value_start`：指定张量的起始位置，以迭代维度中给定的元素
> *   `tensor_value_stop`：指定张量的结束位置，以迭代维度中给定的元素

**示例 1：** Python 代码访问 1 维的所有张量，只得到该维的 7 个值。

```py
# access all the tensors of 1
# dimension and get only 7 values
# in that dimension
print(a[0:1, 0:1, :7])
```

**输出：**

```py
tensor([[[1, 2, 3, 4, 5, 6, 7]]])
```

**例 2：** Python 代码访问所有维度的所有张量，每个维度只得到 3 个值。

```py
# access all the tensors of all
# dimensions and get only 3 values
# in each dimension
print(a[0:1, 0:2, :3])
```

**输出：**

```py
tensor([[[ 1,  2,  3],
        [10, 11, 12]]])
```

**示例 3：** 访问所有张量上一维的 8 个元素。

```py
# access 8 elements in 1 dimension
# on all tensors
print(a[0:2, 1, 0:8])
```

**输出：**

```py
tensor([[10, 11, 12, 13, 14, 15, 16, 17],
       [81, 82, 83, 84, 85, 86, 87, 88]])
```