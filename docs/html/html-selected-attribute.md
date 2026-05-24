# HTML |选中属性

> 原文:[https://www.geeksforgeeks.org/html-selected-attribute/](https://www.geeksforgeeks.org/html-selected-attribute/)

HTML 中的选定属性用于指定页面加载时默认情况下应该选择哪个选项。这是一个布尔属性。默认情况下，将显示具有选定属性的选项。
**语法:**

```html
<option selected>value</option>
```

**注意:**该属性只能在 [<选项>](https://www.geeksforgeeks.org/html-option-selected-attribute/?ref=rp) 元素上使用。
**示例:**在 HTML 程序下面说明所选属性

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>HTML selected Attribute</title>
    </head>
    <body style = "text-align: center;">
        <h1 style = "color: green;">GeeksforGeeks</h1>
        <h2>HTML selected Attribute</h2>

        <!-- List of Options -->
        <select>
            <option value="merge">Merge Sort</option>
            <option value="bubble">Bubble Sort</option>
            <option value="insertion">Insertion Sort</option>

            <!-- Option element with selected attribute -->
            <option value="quick" selected>Quick Sort</option>
        </select>
    </body>
</html>                   
```

**输出:**

![selected](img/ef0b5e0b1d3656cda69122b1ff101bd3.png)

**支持的浏览器:**所选属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队