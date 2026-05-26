# PyTorch `clamp()`方法

> 原文: [https://www.geeksforgeeks.org/python-pytorch-clamp-method/](https://www.geeksforgeeks.org/python-pytorch-clamp-method/)

PyTorch `torch.clamp()`方法将所有输入元素夹在[min, max]范围内，并返回结果张量。
![Clamp method](img/97b0491b205aa089230f024472e1eacd.png)

## 语法
`torch.clamp(inp, min, max, out=None)`

## 参数
* `inp`: 这是输入张量。
* `min`: 这是一个数字，指定输入要箝位到的范围的下限。
* `max`: 这是一个数字，指定输入要箝位到的范围的上限。
* `out`: 输出张量。

## 返回
它返回一个张量。

让我们通过几个例子来理解这个概念：

**示例 1:**
```py
# Importing the PyTorch library 
import torch

# A constant tensor of size n
a = torch.randn(6)
print(a)

# Applying the clamp function and 
# storing the result in 'out'
out = torch.clamp(a, min = 0.5, max = 0.9)
print(out)
```

**输出:**
```py
 -0.9214
-0.1268
 1.1570
-0.2753
-0.0746
 0.7957
[torch.FloatTensor of size 6]
 0.5000
 0.5000
 0.9000
 0.5000
 0.5000
 0.7957
[torch.FloatTensor of size 6]
```

**示例 2:**
```py
# Importing the PyTorch library 
import torch

# A constant tensor of size n
a = torch.FloatTensor([1, 4, 6, 8, 10, 14])
print(a)

# Applying the clamp function and 
# storing the result in 'out'
out = torch.clamp(a, min = 5, max = 10)
print(out) 
```

**输出:**
```py

[torch.FloatTensor of size 6]

[torch.FloatTensor of size 6]?
```