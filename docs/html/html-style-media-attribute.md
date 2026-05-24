# HTML |风格媒体属性

> 原文:[https://www.geeksforgeeks.org/html-style-media-attribute/](https://www.geeksforgeeks.org/html-style-media-attribute/)

“HTML 样式媒体”属性用于指定 CSS 样式优化的媒体或设备。此属性指定特定设备(如打印媒体或语音)的样式。这个属性可以接受几个值。

**语法:**

```html
<style media="value">
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
| 黑白的 | 单色帧缓冲器中的每像素位数。 |
| 解决 | 目标显示器/纸张的像素密度(dpi 或 dpcm)。 |
| 扫描 | 电视显示器的扫描方法。 |
| 格子 | 如果输出设备是网格或位图。 |

**注意:**可以使用**“min-****“max-**等前缀。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        h1 {
            color: green;
        }
    </style>
    <style media="print">
        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <p><a href="https://ide.geeksforgeeks.org/tryit.php" 
              target="_blank">
          Click here
          </a>
    </center>
</body>

</html>
```

**输出:**
![](img/b9f58b6f6f5d7a65b546066aed561ddc.png)

**支持的浏览器:****HTML 风格媒体属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧