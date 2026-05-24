# Python Wand 中的 `charcoal()` 方法

> 原文: [https://www.geeksforgeeks.org/python-charcoal-method-in-wand/](https://www.geeksforgeeks.org/python-charcoal-method-in-wand/)

`charcoal()` 生成原始图像的素描类图像。生成的图像与边缘提取非常相似，颜色相反。作为艺术模拟之一，`charcoal()` 可以模拟纸上的图画。

> **语法:**
> ```py
> wand.image.charcoal(radius, sigma)
> ```
> **参数:**
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | `radius` | 数字。真实的 | 高斯运算符的大小。 |
> | `sigma` | 数字。真实的 | 高斯分布的标准偏差。 |

**来源影像:**
![](img/a1d5dabac07efe8de363e0c440a198d8.png)

## 例 1:
```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:

# Charcoal fx using charcoal() function
    img.charcoal(radius = 1.5, sigma = 0.5)
    img.save(filename ="ch_koala.jpeg")
```
**输出:**
![](img/0d5d622f4cf954e020e90cb5605df2c9.png)

## 例 2: 增加半径和σ值。
```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:

# Charcoal fx using charcoal() function
    img.charcoal(radius = 4, sigma = 0.65)
    img.save(filename ="ch_koala_2.jpeg")
```
**输出:**
![](img/0c3dff2bc0fae3ee804fa2c818442fe3.png)