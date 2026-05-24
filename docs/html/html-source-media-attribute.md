# HTML |源媒体属性

> 原文:[https://www.geeksforgeeks.org/html-source-media-attribute/](https://www.geeksforgeeks.org/html-source-media-attribute/)

HTML 源媒体属性接受通常在 CSS 中定义的任何有效媒体查询。这个属性可以接受几个值。

**语法:**

```html
<source media="media_query">
```

**可能的操作员:**

| 价值 | 描述 |
| 和 | 逻辑积算符 |
| 不 | “非”算符 |
| , | 或运算符 |

**设备:**

| 价值 | 描述 |
| 全部 | 适用于所有设备 |
| 耳的 | 语音合成器 |
| 盲文 | 盲文反馈设备 |
| 手持类型的 | 手持设备(小屏幕，有限带宽) |
| 推断 | 放映机 |
| 打印 | 打印预览模式/打印页面 |
| 屏幕 | 电脑屏幕 |
| 电传打字机 | 使用固定间距字符网格的电传打字机和类似媒体 |
| 电视 | 低分辨率或滚动能力有限的设备，如电视。 |

**值:**

| 价值 | 描述 |
| 宽度 | 目标显示区域的宽度。 |
| 高度 | 目标显示区域的高度 |
| 设备宽度 | 目标显示或纸张宽度。 |
| 设备高度 | 目标显示或纸张高度。 |
| 方向 | 目标显示或纸张方向。 |
| 纵横比 | 目标显示区域的宽高比。 |
| 设备纵横比 | 目标显示器/纸张的设备宽度/设备高度比。 |
| 颜色 | 目标显示器每种颜色的位数。 |
| 颜色指数 | 目标显示器可以处理的颜色数量。 |
| 黑白的 | 单色帧缓冲区中的每像素位数。 |
| 解决 | 目标显示器/纸张的像素密度(dpi 或 dpcm)。 |
| 扫描 | 电视显示器的扫描方法。 |
| 格子 | 如果输出设备是网格或位图。 |

**注意:**可以使用**“min-****“max-**等前缀。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">
</head>

<body>

    <picture>
        <source media="(min-width: 600px)"
                srcset="img1.png">
        <source media="(min-width: 400px)" 
                srcset="img2.png">
        <img src="img3.png" style="width:auto;">
    </picture>

</body>

</html>
```

**输出:**更改浏览器大小。
T3】

![](img/f3dcb6a0c75a93f428a2d45b0f512106.png)

![](img/695c31d021318cf52f42e6df7a441c05.png)

**支持的浏览器:****HTML 源媒体属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧