# CSS | @页面规则

> 原文:[https://www.geeksforgeeks.org/css-page-rule/](https://www.geeksforgeeks.org/css-page-rule/)

**CSS @page 规则**定义了将要打印的页面的尺寸。当您想要打印网页时，有几件重要的事情应该得到控制，如下所列:

*   页面大小、方向、边距、边框和填充。
*   分页符。
*   页眉和页脚。
*   页面计数器。
*   孤儿。

当你遵循@page 规则时，以上所有事情都是可控的。

**语法:**

```html
@page [:left | :right | :first] {
    /* print-specific rules */
} 
```

**页面描述符:**在@page 规则中有三个描述符，它们是:

*   **大小:**指定页面框包含块的大小。

    ```html
    @page {
          size: A4;
     }
    ```

*   **标记:**修剪想要打印的页面很有帮助。

    ```html
    @page {
          marks: crop cross;
     }
    ```

*   **出血:**它扩展了方块

    ```html
    @page {
          bleed: 7pt;
     }
    ```

    的出血区域

**示例:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
<title>CSS @page rule</title>
<style type="text/css">

    /* default for all pages */
    @page {
        margin: 2in;    
    }

    /* margin on left page */
    @page :left {
        margin: 1in;    
    }

    /* margin on right page */
    @page :right {
        margin: 3in;    
    }

    /* top margin on first page */
    @page :first {
        margin-top: 5in;    
    }
    h1{
        color:green;
    }
</style>
</head>
<body>
    <center>
    <h1>GeeksforGeeks</h1>
    <h2>CSS Page At-rule</h2>
    <p>
     If you open output in a new window and print the page
     the margin around the text content appears differently
     than it appears on the screen.
    </p>
    </center>

</body>
</html> 
```

**输出:**当你选择打印上述代码的输出画面时。
T3】

**支持的浏览器:***CSS @ page 规则*支持的浏览器如下:

*   谷歌 Chrome 2.0
*   internet explorer 8.0
*   Safari 5.1
*   Opera 6.0