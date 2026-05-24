# 如何从 PIL 的 URL 打开图片？

> 原文：[https://www.geeksforgeeks.org/how-to-open-an-image-from-the-url-in-pil/](https://www.geeksforgeeks.org/how-to-open-an-image-from-the-url-in-pil/)

在本文中，我们将学习如何使用 Python 中的 PIL 模块从 URL 打开图像。为了从 Python 中的一个网址打开图像，我们需要两个包：`urllib` 和 `Pillow(PIL)`。

## 方法：

1.  安装所需的库，然后导入它们。要安装，请使用以下命令：
    ```
    pip install pillow
    ```
2.  复制任何图像的网址。
3.  在 `urllib.request.urlretrieve()` 方法中写入文件名为的 URL。
4.  使用 `Image.open()` 方法打开图像。
5.  最后用 `obj.show()` 方法显示图像。

## 样本代码：

```py
import urllib.request
from PIL import Image

urllib.request.urlretrieve('Image URL', "file_name")
img = Image.open("file_name")
img.show()
```

## 示例：

### Python 3

```py
# importing modules
import urllib.request
from PIL import Image

urllib.request.urlretrieve(
  'https://media.geeksforgeeks.org/wp-content/uploads/20210318103632/gfg-300x300.png',
   "gfg.png")

img = Image.open("gfg.png")
img.show()
```

## 输出：

![](img/7b7bd75f63720acb95fb357c87949991.png)