# jQuery 选择器是如何执行的？

> 原文:[https://www . geesforgeks . org/how-jquery-selecters-executed/](https://www.geeksforgeeks.org/how-jquery-selectors-are-executed/)

[jQuery](https://www.geeksforgeeks.org/jquery-tutorials/) 是一个快速、轻量级的 JavaScript 库，旨在简化 HTML DOM 树遍历、操作、事件处理、CSS 动画和 Ajax。jQuery 的主要目标是提供一种在网站上使用 JavaScript 的简单方法，使其更具交互性和吸引力。

它以“少写多做”的哲学而闻名因为它是为用很少的代码执行更多的任务而开发的。jQuery 比 JavaScript 更快，因为与 JavaScript 相比，它的代码更少。

**语法:**

```html
 $(selector).action()
```

*   **$–**是定义 jQuery。
*   **选择器–**是在 HTML 页面中查找 HTML 元素。
*   **动作()–**是对所选元素执行的动作。

**jQuery 选择器:** jQuery 选择器用于选择 HTML 元素，并允许您以我们想要的方式操作 HTML 元素。它在一个变量参数上选择 HTML 元素，如它们的名称、类、id、类型、属性、属性值等。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>
    <style>
      body {
        color: green;
        text-align: center;
      }
    </style>
    <script>
      $(document).ready(function () {
        $("button").click(function () {
          $("p").hide();
        });
      });
    </script>
  </head>

  <body>
    <h1>GeeksForGeeks</h1>

    <p>paragraph one.</p>

    <p>paragraph two.</p>

    <button>Click me to hide paragraphs</button>
  </body>
</html>
```

**输出:**

![](img/98e79553a12f4af78ccd9fdd430053a5.png)

jQuery 执行

如果连续处理两个以上的选择器，那么最后一个选择器总是先执行。

例如，jQuery 将首先找到所有带有类”的元素。然后它将选择 id 为“second”的所有元素。

```html
$('p').html($("second.list").text());
```

要了解更多关于 jQuery 选择器的信息，您可以遵循 [jQuery 选择器完整参考](https://www.geeksforgeeks.org/jquery-selectors-complete-reference/)