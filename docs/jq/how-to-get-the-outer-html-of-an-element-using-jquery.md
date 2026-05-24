# 如何使用 jQuery 获取一个元素的外部 html？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery/](https://www.geeksforgeeks.org/how-to-get-the-outer-html-of-an-element-using-jquery/) 获取元素的外部 html

有时，需要通过其 id 而不仅仅是其内容来获取整个 HTML 元素，为此，我们将使用 HTML DOM 外部 HTML 属性来获取 HTML 元素的外部 HTML。

**语法:**

```html
document.getElementById("your-element-id").outerHTML)

```

您可以使用一个变量，并将其初始化为上面的值，以获取外部 HTML 元素的值。下面是一个示例，说明如何获取 HTML 元素的外部 HTML 元素，并将其存储在变量 newVar 中。

**示例 1:** 在本例中，它有一个 div，包含一个带有 **id = "demo"** 的段落。当按下屏幕按钮时，JavaScript 会在浏览器窗口上推送一条警告消息，其中包含具有给定 id 的 HTML 元素的外部 HTML。 **myFunction** 使用 **getElementbyId** 函数获取具有给定 Id 的元素，然后在 HTML 之外获取该元素。如果给定了一个 id，使得有多个 HTML 元素具有该 id，或者没有，那么外部 HTML 将抛出一个错误，因为它是在空值上被调用的。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
    </head>
    <body>
        <div id="demo">

<p>This is the text inside</p>

        </div>

        <button onclick="myFunction()">Try it</button>

        <script>
            function myFunction() {
                var newVar = 
                  document.getElementById("demo").outerHTML;
                alert(newVar);
            }
        </script>
    </body>
</html>
```

**输出:**

```html
<div id="demo">
    <p>This is the text inside</p>
</div>
```

**示例 2:** 这个示例说明了外部 HTML DOM 只显示给定了 id 的 HTML 元素，而不显示其父元素

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
    </head>
    <body>
        <div>
            <p id="demo">This is the text inside</p>

        </div>

        <button onclick="myFunction()">Try it</button>

        <script>
            function myFunction() {
                var newVar = 
                 document.getElementById("demo").outerHTML;
                alert(newVar);
            }
        </script>
    </body>
</html>
```

**输出:**

```html
<p id="demo">This is the text inside</p>
```