# 如何设置 CSS 中引用的标记？

> 原文：[https://www.geeksforgeeks.org/how-to-set-the-marks-for-quotations-in-css/](https://www.geeksforgeeks.org/how-to-set-the-marks-for-quotations-in-css/)

任务是为 CSS 中的引用设置引号。引号 `[" "]` 用于衬托代表引用或口语的材料，引号是 [CSS 引号属性](https://www.geeksforgeeks.org/css-quotes-property/)用于设置引号的类型。

**方法：** 首先创建带有段落元素的 HTML 页面，然后在 `<q>` 元素的帮助下，在适当的地方提供一个引号。

**语法：**

```css
quotes: values;
```

**引号：**

| Entity number | name | output |
| :--- | :--- | :--- |
| \ 0022 | double quotation mark | " |
| \ 0027 | single quotation mark | ' |
| \ 00AB | left-pointing double angle quotation mark | « |
| \ 00BB | right-pointing double angle quotation mark | » |
| \ 2018 | left single quotation mark | ‘ |
| \ 2019 | right single quotation mark | ’ |
| \ 201C | left double quotation mark | “ |
| \ 201D | right double quotation mark | ” |

**示例：**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      body {
        text-align: center;
        font-size: 25px;
      }

      #a {
        quotes: "'" "'";
      }
    </style>
  </head>
  <body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>

    <p><q id="a">
        A computer science portal for geeks
      </q>
    </p>
  </body>
</html>
```

**输出：**

![](img/1d73e672637810c7355d013802565fb6.png)