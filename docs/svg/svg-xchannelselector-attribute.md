# SVG xChannelSelector 属性

> 原文:[https://www . geeksforgeeks . org/SVG-xchannelsele-attribute/](https://www.geeksforgeeks.org/svg-xchannelselector-attribute/)

SVG 中的 xChannelSelector 属性用于指示从*到*的颜色通道，该颜色通道用于沿 x 轴移动中*的像素。只有*<fe 置换贴图>* 元素使用这个属性。*

**语法:**

```html
yChannelSelector = "R | G | B | A"
```

**属性值:**该属性接受四个值，如上所述，如下所述:

*   **R:** 指定在 *in2* 中定义的给定图像的红色通道将用于沿 x 轴移动图像的像素。
*   **G:** 指定在 *in2* 中定义的给定图像的绿色通道将用于沿 x 轴移动图像的像素。
*   **B:** 指定在 *in2* 中定义的给定图像的蓝色通道将用于沿 x 轴移动图像的像素。
*   **A:** 指定在 *in2* 中定义的给定图像的 alpha 通道将用于沿 x 轴移动图像的像素。

**示例 1:** 此示例使用“R”属性值说明了 xChannelSelector 属性的使用。

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

    <body> 
        <h1 style="color: green;"> 
            GeeksforGeeks 
        </h1> 
        <svg width="200" height="200"
            viewBox="0 0 220 220"
            xmlns="http://www.w3.org/2000/svg"> 

        <filter id="geek"> 
            <feTurbulence
            type="turbulence"
            baseFrequency="0.05"
            numOctaves="2"
            result="turbulence"/> 
        <feDisplacementMap in2="turbulence"
            in="SourceGraphic"
            scale="50"
            xChannelSelector="R"
            yChannelSelector="R"/> 
        </filter> 

        <ellipse cx="100" cy="80" 
            rx="100" ry="70"
            style="fill:green;
            filter: url(#geek)"/>
        </svg> 
    </body> 

</html>
```

**输出:**

![](img/0d5d3a0f3e47269cb2b98dc52ae69733.png)

**示例 2:** 此示例使用“R”属性值说明了 xChannelSelector 属性的使用。

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 
    <body> 
        <h1 style="color: green; 
            margin-left: 20px;"> 
            GeeksforGeeks 
        </h1> 
        <svg width="1800"
            height="1800"
            viewBox="25 10 400 400"
            xmlns="http://www.w3.org/2000/svg"> 

        <filter id="geek"> 
            <feTurbulence
            type="turbulence"
            baseFrequency="0.06"
            numOctaves="3"
            result="turbulence"/> 
        <feDisplacementMap
            in2="turbulence"
            in="SourceGraphic"
            scale="10"
            xChannelSelector="R"
            yChannelSelector="G"/> 
        </filter> 

        <polygon points="50 10 55 30 70 30 60
            40 65 55 50 45 35 55 
            40 40 30 30 45 30"
            stroke="green" 
            fill="green" 
            style="filter: url(#geek)"/>
        </svg> 
    </body> 
</html>
```

**输出:**

![](img/feaabcdc384f83b7320fe24a52c7706b.png)