# 如何在 JavaScript 中将多行字符串拆分成行的数组？

> 原文：[https://www.geeksforgeeks.org/how-to-split-multiline-string-into-an-array-of-lines-in-javascript/](https://www.geeksforgeeks.org/how-to-split-multiline-string-into-an-array-of-lines-in-javascript/)

JavaScript 中的多行字符串是指有两行或多行的字符串。要将多行字符串拆分成数组，我们需要在 JavaScript 代码中使用 `split()`。

`split(separator, limit)`：`split()` 函数用于根据我们在其中传递的属性来拆分数据。`separator` 属性指定从这个单词/符号开始划分字符串。`limit` 属性是可选的，它指定将有多少个拆分。

## 例 1

```html
<!DOCTYPE html>
<html>

<body>

<h1>Welcome to Geeks for Geeks</h1>

<button onclick="myFunction()">
        Go
    </button>

<p id="StringToArray"></p>

<script>
        function myFunction() {
            var string = "Are you ready?" 
                + "<br>So let's get started";

            var array = string.split("<br>");

            document.getElementById("StringToArray")
                .innerHTML = array;
        }
    </script>
</body>

</html>
```

**输出：**

![](img/c5697243349ceeb2982afaa7873313d0.png)

在这种情况下，当我们点击“开始”按钮时，多行字符串的数组将显示在屏幕上，用“，”分隔。

## 示例 2

现在，让我们看看如何获取数组的特定索引。

```html
<!DOCTYPE html>
<html>

<body>

<h1>Welcome to Geeks for Geeks</h1>

<button onclick="myFunction()">Go</button>

<p id="StringToArray"></p>

<script>
        function myFunction() {
            var string = "Are you ready?" 
                + "<br>So let's get started";

            var array = string.split("<br>");

            document.getElementById("StringToArray")
                .innerHTML = array[1];
        }
    </script>
</body>

</html>
```

**输出：**

![](img/d2a7cb18f2a1175368a0aecc218a2dfa.png)

当我们写 `array[1]` 时，因此只打印了第二行。如果我们写 `array[2]`，那么它将是 `undefined`，因为这个数组只包含前两个索引中分别为 0 和 1 的数据。

## 示例 3

现在，让我们尝试将字符串作为用户输入。

```html
<!DOCTYPE html>
<html>

<body>
    <h1>Welcome to Geeks for Geeks</h1>

    <textarea id="write" 
        placeholder="Write something" 
        style="height:100px;">
    </textarea>

    <button onclick="myFunction()">Go</button>

    <p id="StringToArray"></p>

    <script>
        function myFunction() {

            var string = document
                .getElementById("write").value;

            var array = string.split(".");

            document.getElementById("StringToArray")
                .innerHTML = array;
        }
    </script>
</body>

</html>
```

**输出：**

![](img/c3d0a82cd0efbf04b92cb6e97582837f.png)