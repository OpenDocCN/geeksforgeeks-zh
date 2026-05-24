# Python–魔杖中的 Image()函数

> 原文: [https://www.geeksforgeeks.org/python-image-function-in-wand/](https://www.geeksforgeeks.org/python-image-function-in-wand/)

在这篇具体的文章中，我们将学习如何通过 Python 棒模块读取我们的图像。要读取魔杖中的图像，我们使用 `Image()` 函数。要操作图像，首先我们需要阅读 Python 中的图像。

> **参数:**
>
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | `image` | `Image` | 制作图像的精确副本 |
> | `blob` | `bytes` | 打开 blob 字节数组的图像 |
> | `file` | `file` | 打开文件对象的图像 |
> | `filename` | `str` | 从文件名打开图像 |
> | `width` | `numbers.Integral` | 新空白图像或从原始数据加载的图像的宽度 |
> | `height` | `numbers.Integral` | 新空白图像或从原始数据加载的图像的高度 |
> | `depth` | `numbers.Integral` | 加载原始数据时使用的深度。 |
> | `background` | `wand.color.Color` | 可选的背景颜色。 |
> | `colorspace` | `str` | 在读取任何图像之前，设置堆栈的默认 `colorspace` 值。 |
> | `units` | `str` | 与分辨率配对，用于定义图像的像素密度。 |

现在我们将编写一个代码来打印图像的高度和宽度。

**代码:**

```py
# import required libraries
from __future__ import print_function
from wand.image import Image

# read image using Image() function
img = Image(filename='koala.jpg')

# print height of image
print('height =', img.height)

# print width of image
print('width = ', img.width)
```

**输出:**

```py
height = 300
width = 400
```

我们还可以使用 `urllib2` 通用 python 库中的 `urlopen` 函数从 url 中读取图像。让我们看看打印从 url 读取的图像高度和宽度的代码。

```py
# import required libraries
from __future__ import print_function
from urllib2 import urlopen
from wand.image import Image

response = urlopen('https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png')
try:
    # read image using Image() function
    img = Image(file=response)

    # print height of image
    print('Height =', img.height)

    # print width of image
    print('Width =', img.width)
finally:
    response.close()
```