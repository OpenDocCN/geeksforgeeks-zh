# JavaScript RegExp 负向先行断言 (?! ) 量词

> 原文: [https://www.geeksforgeeks.org/javascript-regexp-quantifier-4/](https://www.geeksforgeeks.org/javascript-regexp-quantifier-4/)

正则表达式中的 `?!` （负向先行断言）用于查找任何没有后跟特定字符串的字符串匹配。

**语法:**

```
/ pattern?!m /
```

或者

```
new RegExp("pattern?!m")
```

**带修饰符的语法:**

```
/ pattern?!m /g
```

或者

```
new RegExp("pattern?!m", "g")
```

**示例 1:** 此示例匹配整个字符串中没有后跟 `123` 的单词 `"Geeks"`。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        JavaScript RegExp ?! Quantifier
    </title>
</head>

<body style="text-align:center">

<h1 style="color:green">GeeksforGeeks</h1>

<h2>RegExp ?! Quantifier</h2>

<p>Input String: Geeksfor123\nGeeks@</p>

<button onclick="geek()">Click it!</button>

<p id="app"></p>

<script>
        function geek() {
            var str1 = "Geeks for 123 Geeks@";
            var regex4 = /Geeks(?!123)/g;
            var match4 = str1.match(regex4);

            document.getElementById("app").innerHTML
                    = "Found " + match4.length
                    + " matches: " + match4;
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![ques1](img/9bbc7c13c9259ff95df6cc6c2ed62490.png)
**点击按钮后:**
![ques1](img/7fc2c9adf9fc7e42db52186bb56cf205.png)

**示例 2:** 本示例将单词 `"128"` 替换为 `"#"`。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        JavaScript RegExp ?! Quantifier
    </title>
</head>

<body style="text-align:center">

<h1 style="color:green">GeeksforGeeks</h1>

<h2>RegExp ?! Quantifier</h2>

<p>String: @128Geek128</p>

<button onclick="geek()">Click it!</button>

<p id="app"></p>

<script>
        function geek() {
            var str1 = "@128Geek128";
            var regex4 = new RegExp("128(?!ee)", "gi");         
            var replace = "#";
            var match4 = str1.replace(regex4, replace);
            document.getElementById("app").innerHTML = 
                " New string: " + match4;
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![ques1](img/e159f3f697fb77c8fb2b5f9a09f14343.png)
**点击按钮后:**
![ques1](img/199fca905b19a81da7f0f8fef143d4d9.png)

**支持的浏览器:** `RegExp` 的 `?!` 负向先行断言支持的浏览器如下:

*   谷歌 Chrome
*   苹果 Safari
*   Mozilla Firefox
*   歌剧
*   微软公司出品的 web 浏览器