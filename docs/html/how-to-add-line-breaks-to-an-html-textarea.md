# 如何给 HTML 文本区域添加换行符？

> 原文:[https://www . geesforgeks . org/如何将换行符添加到 html-textarea/](https://www.geeksforgeeks.org/how-to-add-line-breaks-to-an-html-textarea/)

实现换行符的方式因平台而异。以下方法从 HTML 文本区域获取输入文本，并使用 JavaScript 添加换行符。

**方法:**
这个任务可以通过使用 JavaScript 提供的一些预定义的数组和字符串函数来实现。在下面的代码中，来自 textarea 的输入由 JavaScript 在单击 submit 按钮时进行处理，以生成带有换行符的所需输出。

**使用的函数:**
**[split():](https://www.geeksforgeeks.org/javascript-string-prototype-split-function/)** 是一个预定义的 JavaScript 函数，使用参数将字符串拆分为数组。
**[join():](https://www.geeksforgeeks.org/javascript-array-prototype-join-function/)** 是一个预定义的 JavaScript 函数，它连接一个数组，使用提供的参数将其转换为字符串。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>

    <script type="text/javascript">
        function divide() {
            var txt;
            txt = document.getElementById('a').value;
            var text = txt.split(".");
            var str = text.join('.</br>');
            document.write(str);
        }
    </script>
    <title></title>
</head>

<body>
    <form>
        ENTER TEXT:
        <br>
        <textarea rows="20" 
                  cols="50" 
                  name="txt" 
                  id="a">
      </textarea>
        <br>
        <br>
        <input type="submit" 
               name="submit"
               value="submit" 
               onclick="divide()" />
    </form>
</body>

</html>
```

**输出:**
**无断行代码:**

```html
Geeks for geeks. Geeks for geeks. Geeks for geeks. Geeks for geeks.
```

**断行代码:**

```html
Geeks for geeks. 
Geeks for geeks. 
Geeks for geeks. 
Geeks for geeks.
```