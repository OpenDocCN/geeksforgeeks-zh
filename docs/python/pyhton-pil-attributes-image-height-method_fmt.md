# Python PIL `Image.height` 属性方法

> 原文: [https://www.geeksforgeeks.org/pyhton-pil-attributes-image-height-method/](https://www.geeksforgeeks.org/pyhton-pil-attributes-image-height-method/)

PIL 是 Python 图像库，它为 Python 解释器提供图像编辑功能。`Image` 模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`Image` 类具有 `height` 属性。

## `Image.height`
图像高度，以像素为单位。该属性定义了对象、元素或文件的各种属性。

## 语法
`PIL.Image.height`

## 参数
`Image` – 图像用于不同的延伸。

## 返回值
图像的高度。

## 所用图像
![](img/7dcee0f4c2b8e9d23dccc651065d73ab.png)

## 代码示例
```py
# importing Image module from PIL package 
from PIL import Image

# opening a image 
im = Image.open(r"C:\Users\System-Pc\Desktop\flower1.jpg")

# height attribute
im1 = im.height
print(im1)
```

## 输出
```py

```

## 另一个例子
用拍摄另一个图像。png 扩展名。

## 所用图像
![](img/686ce0abe8be10b924d2c483da582a22.png)

## 代码示例
```py
# importing Image module from PIL package 
from PIL import Image

# opening a image 
im = Image.open(r"C:\Users\System-Pc\Desktop\python.png")

# height attribute
im1 = im.height
print(im1)
```

## 输出
```py

```