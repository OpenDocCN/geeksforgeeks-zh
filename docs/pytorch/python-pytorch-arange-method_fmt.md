# Python PyTorch 的 `arange()` 方法

> 原文: [https://www.geeksforgeeks.org/python-pytorch-arange-method/](https://www.geeksforgeeks.org/python-pytorch-arange-method/)

PyTorch 是 Facebook 开发的开源机器学习库。它用于深度神经网络和自然语言处理。
函数 `torch.arange()` 返回大小为 $\left\lceil \frac{\text{end} - \text{start}}{\text{step}} \right\rceil$ 的一维张量，其值来自区间 $[\text{start}, \text{end})$，以公共差 `step` 递增。
$\text{out}_{i+1} = \text{out}_i + \text{step}$

## 语法
`torch.arange(start=0, end, step=1, out=None)`

## 参数
- **start** (`float`, 可选): 该组点的起始值。默认值: `0`。
- **end** (`float`): 该组点的结束值。
- **step** (`float`, 可选): 每对相邻点之间的间隙。默认值: `1`。
- **out** (`Tensor`, 可选): 输出张量。

## 返回类型
`Tensor`

## 代码示例

### Python 3

```py
# Importing the PyTorch library
import torch

# Applying the arrange function and
# storing the resulting tensor in 't'
a = torch.arange(3)
print("a = ", a)

b = torch.arange(1, 6)
print("b = ", b)

c = torch.arange(1, 5, 0.5)
print("c = ", c)
```

### 输出

```py
a =  tensor([0, 1, 2])
b =  tensor([1, 2, 3, 4, 5])
c =  tensor([1.0000, 1.5000, 2.0000, 2.5000, 3.0000, 3.5000, 4.0000, 4.5000])
```

请注意，在与 `end` 进行比较时，非整数 `step` 会受到浮点舍入误差的影响；为了避免不一致，我们建议在这种情况下在末尾添加一个小的 `epsilon`。