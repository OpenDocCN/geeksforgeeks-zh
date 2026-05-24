# HTML | DOM 输出 htmlFor Property

> 原文:[https://www . geesforgeks . org/html-DOM-output-html for-property/](https://www.geeksforgeeks.org/html-dom-output-htmlfor-property/)

**HTML DOM 输出 htmlFor 属性**用于返回<输出>元素的 For 属性的值。 **htmlFor** 属性用于指定结果和计算之间的关系。

**语法:**

```html
outputObject.htmlFor 
```

**参数:**该属性不接受任何参数。
**返回值:**返回一个**元素 _id** ，表示结果与计算的关系。

**示例:**本示例返回一个 htmlFor 属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Output htmlFor Property
    </title>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2> 
     HTML DOM Output htmlFor Property 
    </h2>
    <form oninput="sumresult.value = parseInt(A.value) 
                + parseInt(B.value) + parseInt(C.value)">
        <input type="number" name="A" value="50" /> +

        <input type="range" name="B" value="0" /> +

        <input type="number" name="C" value="50" />
        <br /> Submit Result:
        <output name="sumresult" id="geeks" for="A B C">
        </output>
        <br>
        <br>
    </form>
    <Button onclick="myGeeks()">Submit</Button>
    <h2 id="sudo"></h2>

    <script>
        function myGeeks() {
            var x = document.getElementById("geeks").htmlFor;
            document.getElementById("sudo").innerHTML = x;
        }
    </script>

</body>

</html>
```

**输出:**

*   点击按钮前:
    ![](img/fe04d5385400fff30b762092dde685ea.png)
*   点击按钮后:
    ![](img/f311d944fdfcfa02f429380c3db3da56.png)

**支持的浏览器:**属性的 *HTML DOM 输出 HTML 支持的浏览器如下:*

*   google chrome 10.0
*   Firefox 4.0
*   Opera 11.0
*   Safari 5.1