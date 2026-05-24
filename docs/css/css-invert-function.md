# CSS |反转()功能

> 原文:[https://www.geeksforgeeks.org/css-invert-function/](https://www.geeksforgeeks.org/css-invert-function/)

**反转()功能**是一个内置功能，用于对图像应用滤镜来设置样本图像颜色的反转。

**语法:**

```html
invert( amount )
```

**参数:**该功能接受单参数**金额**，保存折算金额。反转的值是根据值和百分比设置的。值 0%代表原始图像，100%代表反转图像。

**反演()**函数在内部使用以下公式来计算图像的反演:

```html
amount * (255 - value) + (1 - amount) * value
```

反转值由变量`amount`控制，变量值位于**0–1**(浮动)范围内(这是通过将颜色反转的通过百分比转换为 0-1 之间的值来实现的)。**值**是像素的颜色值。`(255-value)`用最大像素值减去颜色值后给出颜色，假设像素值在范围**0–255**内(尽管输入图像样本空间可以拉伸/缩放以满足指定标准)。

下表列出了反转百分比及其产生的结果。

| **反转** | **结果** |
| **0%** | **原始图像** |
| **50%** | **每个像素具有灰色的图像** |
| **100%** | **完全反转图像** |

下面的例子说明了 **CSS invert()函数**在 CSS 中:
T3】例子:

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>CSS invert() Function</title> 

    <style>
        h1 {
            color:green;
        }
        body {
            text-align:center;
        }
        .invert_effect {
            filter: invert(100%);
        }
    </style>
</head> 

<body> 
    <h1>GeeksforGeeks</h1> 

    <h2>CSS invert() function</h2>

    <img class="invert_effect" src= 
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
        alt="GeeksforGeeks logo"> 
</body> 

</html>
```

**输出:**
![](img/7f1f0ece09d164c20634a38216a733f6.png)

**支持的浏览器:**invert()函数支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧