# 如何在 HTML 中包含 HTML 代码片段？

> 原文:[https://www . geesforgeks . org/how-to-include-html-code-snippets-in-html/](https://www.geeksforgeeks.org/how-to-include-html-code-snippets-in-html/)

在本文中，我们将学习如何在 HTML 代码中包含 HTML 片段。我们将把“*gfg.html*”的 HTML 代码片段包含到“*index.html*”中。为了实现这个任务，我们将在“*index.html*”中编写一个 JavaScript 函数，该函数遍历“*gfg . HTML”*中所有 HTML 元素的集合，并搜索具有特定属性的元素。它创建一个以属性值作为文件名的 HTTP 请求。最后，我们将区分主“*index.html*”文件和收录的“*gfg.html*”片段。

**进场:**

*   创建两个 HTML 文件“*index.html*”和“*gfg.html*”。
*   创建另一个包含“*index . HTML”*文件的 HTML 文件。
*   在主 HTML 文件中创建一个 [JavaScript 函数](https://www.geeksforgeeks.org/functions-in-javascript/)，用于包含 HTML 片段。
*   调用 main(*“index . html*”)文件中的函数，包含“*gfg.html*的片段”。

**第一步:**创建名为“index.html”的主 HTML 文件。该文件将显示标题文本“这是索引. html”。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h1 align='center'>
        <font color='Red'>
            This is index.html 
        </font>
    </h1>
</body>

</html>
```

**输出:**

![](img/ab0fdde55ea1d97aa932db1b3687a200.png)

**第二步**:创建另一个你选择的 HTML 文件，包含在“*index.html*文件中，并将该文件保存在存在“*index.html*的同一目录中。在本文中，创建一个名为“*gfg.html*的 HTML 文件，其中显示了“极客的电脑科学门户”。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<style>
    body {
        text-align: center;
    }

    .gfg {
        font-size: 180px;
        font-weight: bold;
        color: green;
    }

    .geeks {
        font-size: 50px;
        font-weight: bold;
        font-family: Arial;
    }
</style>

<body>
    <div class="gfg">GeeksforGeeks</div>
    <div class="geeks">
        A computer science portal for geeks
    </div>

    <h1>
        <font color='Blue'>
            This is gfg.html 
        </font>
    </h1>
</body>

</html>
```

**输出:**

![](img/145bb29d76ccf9df3d19de27f37e7924.png)

**第三步:**我们将把“*gfg.html*片段包含在“*index.html*文件中。包含 HTML 是通过使用*GFG-包含-HTML-片段*属性来完成的。

```html
<div GFG-include-html-snippet="gfg.html"></div>
```

**添加 JavaScript**

*   遍历所有 HTML 元素的集合。
*   搜索具有特定属性的元素。
*   创建一个以属性值作为文件名的 HTTP 请求。
*   删除该属性并再次调用该函数。
*   退出功能。

**JavaScript 代码片段:**

## java 描述语言

```html
<script>
    function includeHTMLSnippet() {

        // Traverse the collection of all
        // HTML elements
        id = document.getElementsByTagName("*");
        for (i = 0; i < id.length; i++) {
            element = id[i];

            // Search for elements with
            // specific attributes
            file = element.getAttribute(
                "GFG-include-html-snippet");

            if (file) {

                // Create an HTTP request with 
                // the attribute value as the
                // file name
                xmlRequest = new XMLHttpRequest();
                xmlRequest.onreadystatechange = function () {
                    if (this.readyState == 4) {
                        if (this.status == 200) { 
                            element.innerHTML = this.responseText; 
                        }

                        if (this.status == 404) { 
                            element.innerHTML = "Page not found."; 
                        }

                        // Delete the attribute and
                        // call this function again.
                        element.removeAttribute(
                            "GFG-include-html-snippet");

                        includeHTMLSnippet();
                    }
                }
                xmlRequest.open("GET", file, true);
                xmlRequest.send();
                return; // Exit function.
            }
        }
    };
</script>
```

**第四步:**调用页面底部的**includehtmlsnept()**。

```html
<script>
    includeHTMLSnippet();
</script>
```

**最终代码:**以下代码演示了上述所有步骤的组合。

## index.html

```html
<!DOCTYPE html>
<html>

<head>
    <script>
        function includeHTMLSnippet() {

            // Traverse the collection of
            // all HTML elements
            id = document.getElementsByTagName("*");
            for (i = 0; i < id.length; i++) {
                element = id[i];

                // Search for elements with
                // specific attributes
                file = element.getAttribute(
                    "GFG-include-html-snippet");

                if (file) {

                    // Create an HTTP request with the 
                    // attribute value as the file name
                    xmlRequest = new XMLHttpRequest();
                    xmlRequest.onreadystatechange = function () {
                        if (this.readyState == 4) {
                            if (this.status == 200) { 
                                element.innerHTML = this.responseText; 
                            }

                            if (this.status == 404) { 
                                element.innerHTML = "Page not found.";
                            }

                            // Delete the attribute and
                            // call this function again
                            element.removeAttribute(
                                "GFG-include-html-snippet");

                            includeHTMLSnippet();
                        }
                    }
                    xmlRequest.open("GET", file, true);
                    xmlRequest.send();
                    return; // Exit function.
                }
            }
        };
    </script>
</head>

<body>
    <h1 align='center'>
        <font color='Red'>
            This is index.html 
        </font>
    </h1>

    <div GFG-include-html-snippet="gfg.html"></div>

    <script>
        includeHTMLSnippet();
    </script>
</body>

</html>
```

## gfg.html 格式

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            text-align: center;
        }

        .gfg {
            font-size: 140px;
            font-weight: bold;
            color: green;
        }

        .geeks {
            font-size: 50px;
            font-weight: bold;
            font-family: Arial;
        }
    </style>
</head>

<body>
    <div class="gfg">
        GeeksforGeeks
    </div>

    <div class="geeks">
        A computer science portal for geeks
    </div>

    <h1>
        <font color='Blue'>
            This is gfg.html
        </font>
    </h1>
</body>

</html>
```

**输出:**

![](img/e0769f8c1f6ca17f19db0d6480103280.png)

**区分 index.html 中包含的 gfg.html 片段:**红色边框表示主*index.html*的输出，蓝色边框表示包含的 html 片段的输出。

![](img/5a73b198ec3dec988fc22832edc197d9.png)