# jQuery 中如何按 ID 选择元素？

> 原文:[https://www . geesforgeks . org/如何在 jquery 中按 id 选择元素/](https://www.geeksforgeeks.org/how-to-select-element-by-id-in-jquery/)

在本文中，我们将看到如何使用 jQuery 通过元素的 id 来选择元素。要了解这个主题，你应该先了解 HTML、CSS、JavaScript 和 jQuery。

**使用 JavaScript:** 这个问题也是通过一个流行的 JavaScript 方法来解决的，这个方法叫做[**d*****document . getelementbyId()***](https://www.geeksforgeeks.org/html-dom-getelementbyid-method/)*，用来通过元素的 id 属性来选择元素。getElementById()方法返回具有给定标识的元素，该标识被传递给函数。这个函数在网页设计中被广泛使用来改变任何特定元素的值或者得到一个特定的元素。如果传递给函数的标识不存在，则返回空值。*

***语法:***

```html
*document.getElementById('idname')* 
```

***示例:***

## *超文本标记语言*

```html
*<!DOCTYPE html>
<html>

<head>
    <title>
        How do you select element by ID in javascript?
    </title>
</head>

<body style="border: 2px solid green; 
    min-height: 240px; text-align: center;">

    <h1 style="color:green;">
        GeeksforGeeks
    </h1>

    <p id="element" style="margin-top:20px;"></p>

    <script>
        setTimeout(function() {
            document.getElementById('element').innerText 
                = 'Hello Geeks !! Welcome to GeeksforGeeks';
        }, 2000);
    </script>
</body>

</html>*
```

 ***输出:**

![](img/12733a8ffda324517c7a027395c661c1.png)

**使用 jQuery:** 上面的代码也是使用 jQuery 方法完成的，非常简单，用的代码也比较少。 [**#id 选择器**](https://www.geeksforgeeks.org/jquery-id-selector/) 指定要选择的元素的 id。它不应该以数字开头，并且 id 属性在文档中必须是唯一的，这意味着它只能使用一次。

**语法:**

```html
$("#idname");
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How do you select element 
        by ID in javascript?
    </title>

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js">
    </script>
</head>

<body style="border: 2px solid green; 
    min-height: 240px; text-align: center;">

    <h1 style="color:green;">
        GeeksforGeeks
    </h1>

    <p id="element" style="margin-top:20px;"></p>

    <script>
        setTimeout(function () {
            $('#element').text(
                'Hello Geeks !! Welcome to GeeksforGeeks');
        }, 2000);
    </script>
</body>

</html>
```

**输出:**

![](img/12733a8ffda324517c7a027395c661c1.png)*