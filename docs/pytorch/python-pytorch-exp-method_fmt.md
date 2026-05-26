# PyTorch `exp()` 方法

> 原文：[https://www.geeksforgeeks.org/python-pytorch-exp-method/](https://www.geeksforgeeks.org/python-pytorch-exp-method/)

PyTorch 的 `torch.exp()` 方法在计算输入张量各元素的指数后，返回一个新的张量。
![exp method](img/e8682b9011ae1bdee5775d20d75ee506.png)

## 语法

`torch.exp(input, out=None)`

## 参数

*   `input`：输入张量。
*   `out`：输出张量。

## 返回值

返回一个张量。

## 示例

让我们通过几个例子来理解这个概念：

### 示例 1

```py
# Importing the PyTorch library 
import torch

# A constant tensor of size n
a = torch.randn(6)
print(a)

# Applying the exp function and 
# storing the result in 'out'
out = torch.exp(a)
print(out)
```

**输出：**

```py
 1.0532
-1.9300
 0.6392
-0.7519
 0.9133
 0.3998
[torch.FloatTensor of size 6]
 2.8667
 0.1451
 1.8949
 0.4715
 2.4925
 1.4915
[torch.FloatTensor of size 6]
```

### 示例 2

```py
# Importing the PyTorch library 
import torch

# A constant tensor of size n
a = torch.FloatTensor([1, 4, 6, 3])
print(a)

# Applying the exp function and 
# storing the result in 'out'
out = torch.exp(a)
print(out)
```

**输出：**

```py
[torch.FloatTensor of size 4]
   2.7183
  54.5981
 403.4288
  20.0855
[torch.FloatTensor of size 4]
```