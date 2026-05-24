# 2 位二进制输入或非门感知器算法的实现

> 原文：[https://www.geeksforgeeks.org/implementation-of-perceptron-algorithm-for-nor-logic-gate-with-2-bit-binary-input/](https://www.geeksforgeeks.org/implementation-of-perceptron-algorithm-for-nor-logic-gate-with-2-bit-binary-input/)

在机器学习领域，感知器是一种用于二进制分类器的监督学习算法。感知器模型实现以下功能：

![\[ \begin{array}{c} \hat{y}=\Theta\left(w_{1} x_{1}+w_{2} x_{2}+\ldots+w_{n} x_{n}+b\right) \\ =\Theta(\mathbf{w} \cdot \mathbf{x}+b) \\ \text { where } \Theta(v)=\left\{\begin{array}{cc} 1 & \text { if } v \geqslant 0 \\ 0 & \text { otherwise } \end{array}\right. \end{array} \]](img/7a525c5fa0f2cf3118ef7158b4d5b176.png "Rendered by QuickLaTeX.com")

对于权重向量`w`和偏差参数`b`的特定选择，模型预测相应输入向量`x`的输出`\hat{y}`。

**2 位二进制变量** 的 NOR 逻辑函数真值表，即输入向量`x : (x_{1}, x_{2})`和相应的输出`y`：

| `x_{1}` | `x_{2}` | `y` |
| --- | --- | --- |
| Zero | Zero | one |
| Zero | one | Zero |
| one | Zero | Zero |
| one | one | Zero |

我们可以观察到，`NOR(x_{1}, x_{2}) = NOT(OR(x_{1}, x_{2}))`。
现在对于输入向量`x : (x_{1}, x_{2})`到 or 节点的对应权重向量`w : (w_{1}, w_{2})`，关联的感知器函数可以定义为：

![\[ \boldsymbol{\hat{y}\prime} = \Theta\left(w_{1} x_{1}+w_{2} x_{2}+b_{OR}\right) \]](img/d2d050a0a29060d4a92cb4c31532dfc7.png "Rendered by QuickLaTeX.com")

稍后，或节点`\hat{y}\prime`的输出是权重为`w_{NOT}`的非节点的输入。那么相应的输出`\hat{y}`就是或非门逻辑函数的最终输出，相关的感知器函数可以定义为：

![\[ \boldsymbol{\hat{y}} = \Theta\left(w_{NOT}  \boldsymbol{\hat{y}\prime}+b_{NOT}\right) \]](img/e45e0c382856a6cc1b3c3f47d5337dfb.png "Rendered by QuickLaTeX.com")

![](img/4de94068b828ff4c2ad10856d4a7bb11.png)
为实现，考虑的权重参数为`w_{1} = 1, w_{2} = 1, w_{NOT} = -1`，偏差参数为`b_{OR} = -0.5, b_{NOT} = 0.5`。

**Python 实现：**

```py
# importing Python library
import numpy as np

# define Unit Step Function
def unitStep(v):
    if v >= 0:
        return 1
    else:
        return 0

# design Perceptron Model
def perceptronModel(x, w, b):
    v = np.dot(w, x) + b
    y = unitStep(v)
    return y

# NOT Logic Function
# wNOT = -1, bNOT = 0.5
def NOT_logicFunction(x):
    wNOT = -1
    bNOT = 0.5
    return perceptronModel(x, wNOT, bNOT)

# OR Logic Function
# w1 = 1, w2 = 1, bOR = -0.5
def OR_logicFunction(x):
    w = np.array([1, 1])
    bOR = -0.5
    return perceptronModel(x, w, bOR)

# NOR Logic Function
# with OR and NOT   
# function calls in sequence
def NOR_logicFunction(x):
    output_OR = OR_logicFunction(x)
    output_NOT = NOT_logicFunction(output_OR)
    return output_NOT

# testing the Perceptron Model
test1 = np.array([0, 1])
test2 = np.array([1, 1])
test3 = np.array([0, 0])
test4 = np.array([1, 0])

print("NOR({}, {}) = {}".format(0, 1, NOR_logicFunction(test1)))
print("NOR({}, {}) = {}".format(1, 1, NOR_logicFunction(test2)))
print("NOR({}, {}) = {}".format(0, 0, NOR_logicFunction(test3)))
print("NOR({}, {}) = {}".format(1, 0, NOR_logicFunction(test4)))
```

**Output：**

```py
NOR(0, 1) = 0
NOR(1, 1) = 0
NOR(0, 0) = 1
NOR(1, 0) = 0
```

这里，根据 2 位二进制输入的真值表，每个测试输入的模型预测输出(`\hat{y}`)与或非门常规输出(`y`)完全匹配。
验证了或非门感知器算法的正确实现。