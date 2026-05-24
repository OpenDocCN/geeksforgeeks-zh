# Python–在魔杖中评估()函数

> 原文:[https://www . geesforgeks . org/python-evaluate-function-in-wand/](https://www.geeksforgeeks.org/python-evaluate-function-in-wand/)

在 `evaluate()` 函数中，可以通过应用算术、关系或逻辑表达式来操作像素通道。

## 语法

```py
wand.image.evaluate(operator, value, channel)
```

## 参数

| 参数 | 输入类型 | 描述 |
| --- | --- | --- |
| `operator` | 基绳 | 要计算的操作类型。 |
| `value` | 数字。真实的 | 用运算符计算的数字 |
| `channel` | 基绳 | 对其应用操作的可选通道。 |

以下是魔杖中的评估操作列表:

| 评估操作 | 描述 |
| --- | --- |
| `'undefined'` | 它是默认的 `EVALUATE_OPS`。 |
| `'abs'` | 创建一个抽象评估。 |
| `'add'` | 添加评估。 |
| `'addmodulus'` | 添加模数评估。 |
| `'and'` | 和评估。 |
| `'cosine'` | 从余弦函数计算。 |
| `'gaussiannoise'` | 添加高斯噪声评估 |
| `'impulse noise'` | 添加脉冲噪声评估 |
| `'laplacian noise'` | 添加拉普拉斯噪声评估 |
| `'left shift'` | 按位左移位 |
| `'max'` | 最大评估 |
| `'mean'` | 添加了均值评估。 |
| `'median'` | 添加了中值评估。 |
| `'multiplicative noise'` | 添加乘法噪声评估 |
| `'multiply'` | 多重图像评估 |
| `'or'` | 或评估 |
| `'poissonnoise'` | 添加泊松噪声评估 |
| `'pow'` | 添加功耗评估 |
| `'right shift'` | 按位右移 |
| `'set'` | 添加集合评估 |
| `'sine'` | 添加正弦函数评估 |
| `'threshold'` | 添加具有特定阈值点的阈值评估。 |
| `'thresholdblack'` | 阈值为黑色时添加评估。 |
| `'thresholdwhite'` | 阈值为白色时添加评估。 |
| `'uniformnoise'` | 添加均匀噪声评估 |

**来源图片:**

![](img/a1d5dabac07efe8de363e0c440a198d8.png)

## 代码示例 1

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    img.evaluate(operator ='rightshift', value = 1, channel ='blue')
    img.save(filename ="kl-enhanced.jpeg")
```

**输出图像:**

![](img/66f14398c5e47a72e7afe7940884c22f.png)

## 代码示例 2

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    img.evaluate(operator ='leftshift', value = 1, channel ='red')
    img.save(filename ="kl-enhanced2.jpeg")
```

**输出图像:**

![](img/66648003f638c7aae885ae6fdc8bba6e.png)