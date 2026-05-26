# 如何正确访问 3D Pytorch 张量中的元素？

> 原文: [https://www.geeksforgeeks.org/how-to-correctly-access-elements-in-a-3d-pytorch-tensor/](https://www.geeksforgeeks.org/how-to-correctly-access-elements-in-a-3d-pytorch-tensor/)

在本文中，我们将讨论如何在 Pytorch 中访问三维张量中的元素。PyTorch 是一个优化的张量库，主要用于使用图形处理器和中央处理器的深度学习应用程序。它是广泛使用的机器学习库之一，其他的还有 TensorFlow 和 Keras。Python 支持 `torch` 模块，因此要使用这个模块，我们首先要将模块导入到工作空间中。

**语法**:

```python
import torch
```

我们可以使用 `torch.tensor()` 函数创建一个向量。

**语法:**

```python
torch.tensor([value1, value2, ... value n])
```

## 示例 1: 创建三维张量并显示

```py
# import torch module
import torch

# create an 3 D tensor with 8 elements each
a = torch.tensor([[[1, 2, 3, 4, 5, 6, 7, 8],
                   [10, 11, 12, 13, 14, 15, 16, 17]],
                  [[71, 72, 73, 74, 75, 76, 77, 78],
                   [81, 82, 83, 84, 85, 86, 87, 88]]])

# display actual  tensor
print(a)
```

**输出:**

```py
tensor([[[ 1,  2,  3,  4,  5,  6,  7,  8],
        [10, 11, 12, 13, 14, 15, 16, 17]],
       [[71, 72, 73, 74, 75, 76, 77, 78],
        [81, 82, 83, 84, 85, 86, 87, 88]]])
```

要从三维张量访问元素，可以使用切片。切片意味着通过使用 `:` 切片操作符来选择张量中存在的元素。我们可以通过使用特定元素的索引来分割元素。

**注**: 索引从 0 开始。

**语法:**

```python
tensor[tensor_position_start:tensor_position_end, tensor_dimension_start:tensor_dimension_end, tensor_value_start:tensor_value_end]
```

其中，

*   `tensor_position_start` – 指定开始迭代的张量
*   `tensor_position_end` – 指定停止迭代的张量
*   `tensor_dimension_start` – 指定在给定位置开始张量迭代的张量
*   `tensor_dimension_stop` – 指定张量在给定位置停止张量的迭代
*   `tensor_value_start` – 指定张量的开始位置，以迭代维度中给定的元素
*   `tensor_value_stop` – 指定张量的结束位置，以迭代维度中给定的元素

下面给出了相同的各种例子。

## 示例 2: 访问 1 维的所有张量，只得到该维的 7 个值

```py
# import torch module
import torch

# create an 3 D tensor with 8 elements each
a = torch.tensor([[[1, 2, 3, 4, 5, 6, 7, 8], 
                   [10, 11, 12, 13, 14, 15, 16, 17]], 
                  [[71, 72, 73, 74, 75, 76, 77, 78], 
                   [81, 82, 83, 84, 85, 86, 87, 88]]])

# display actual  tensor
print(a)

# access  all the tensors of 1  dimension 
# and get only 7 values in that dimension
print(a[0:1, 0:1, :7])
```

**输出:**

```py
tensor([[[ 1,  2,  3,  4,  5,  6,  7,  8],
        [10, 11, 12, 13, 14, 15, 16, 17]],
       [[71, 72, 73, 74, 75, 76, 77, 78],
        [81, 82, 83, 84, 85, 86, 87, 88]]])
tensor([[[1, 2, 3, 4, 5, 6, 7]]])
```

## 示例 3: 访问所有维度的所有张量，每个维度只得到 3 个值

```py
# import torch module
import torch

# create an 3 D tensor with 8 elements each
a = torch.tensor([[[1, 2, 3, 4, 5, 6, 7, 8],
                   [10, 11, 12, 13, 14, 15, 16, 17]], 
                  [[71, 72, 73, 74, 75, 76, 77, 78], 
                   [81, 82, 83, 84, 85, 86, 87, 88]]])

# display actual  tensor
print(a)

# access  all the tensors of all dimensions
# and get only 3 values in each dimension
print(a[0:1, 0:2, :3])
```

**输出:**

```py
tensor([[[ 1,  2,  3,  4,  5,  6,  7,  8],
        [10, 11, 12, 13, 14, 15, 16, 17]],
       [[71, 72, 73, 74, 75, 76, 77, 78],
        [81, 82, 83, 84, 85, 86, 87, 88]]])
tensor([[[ 1,  2,  3],
        [10, 11, 12]]])
```

## 示例 4: 访问所有张量上一维的 8 个元素

```py
# import torch module
import torch

# create an 3 D tensor with 8 elements each
a = torch.tensor([[[1, 2, 3, 4, 5, 6, 7, 8], 
                   [10, 11, 12, 13, 14, 15, 16, 17]], 
                  [[71, 72, 73, 74, 75, 76, 77, 78], 
                   [81, 82, 83, 84, 85, 86, 87, 88]]])

# display actual  tensor
print(a)

# access 8 elements in 1 dimension on all tensors
print(a[0:2, 1, 0:8])
```

**输出:**

```py
tensor([[[ 1,  2,  3,  4,  5,  6,  7,  8],
        [10, 11, 12, 13, 14, 15, 16, 17]],
       [[71, 72, 73, 74, 75, 76, 77, 78],
        [81, 82, 83, 84, 85, 86, 87, 88]]])
tensor([[10, 11, 12, 13, 14, 15, 16, 17],
       [81, 82, 83, 84, 85, 86, 87, 88]])
```