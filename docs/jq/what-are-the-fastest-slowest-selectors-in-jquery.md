# jQuery 中最快/最慢的选择器有哪些？

> 原文:[https://www . geesforgeks . org/什么是 jquery 中最快最慢的选择器/](https://www.geeksforgeeks.org/what-are-the-fastest-slowest-selectors-in-jquery/)

jQuery [**选择器**](https://www.geeksforgeeks.org/jquery-selectors-and-event-methods/) 用于选择和操纵 HTML 元素。

在 jQuery 中，主要有三个选择器。

*   身份选择器
*   类别选择器
*   元素选择器

在继续之前，首先，让我们简单地看看这些选择器是如何使用的。

**元素选择器:** jQuery 元素选择器根据元素的名称选择元素。

**语法:**

```html
$(''element")
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>

<head>
    <!-- jQuery library -->
    <script src=
        "https://code.jquery.com/jquery-git.js">
    </script>

    <style>
        p {
            font-size: 25px;
        }
    </style>
</head>

<body>

    <p>GeeksForGeeks</p>

    <script>

        // Element selector
        $("p").css("color", "red");
    </script>
</body>

</html>
```

**输出:**

![](img/fd6c4681a5cae3613922e2dc91b175bb.png)

[**ID 选择器:**](https://www.geeksforgeeks.org/css-id-selector/)jQuery**# ID**选择器根据 HTML 标签的 [ID](https://www.geeksforgeeks.org/html-id-attributes/) 属性选择元素。

这个选择器基本上是在我们必须处理单个元素时使用的，因为一个标识在网页中应该是唯一的。

**语法:**

```html
$("#ID")
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>

<head>
    <!-- jQuery library -->
    <script src=
        "https://code.jquery.com/jquery-git.js">
    </script>

    <style>
        p {
            font-size: 25px;
        }
    </style>
</head>

<body>
    <p>GeeksForGeeks</p>

    <p id="first">Hello Geeks</p>

    <script>

        // ID selector
        $("#first").css("color", "red");
    </script>
</body>

</html>
```

**输出:**

![](img/21fb7f658bcbf2c66c5d1a7d132d328f.png)

身份选择器

[**类选择器:**](https://www.geeksforgeeks.org/css-class-selector/)jQuery**。类别**选择器选择类别匹配的元素或元素集。不同的 HTML 元素允许使用相同的类名。

**语法:**

```html
$(".class")
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>

<head>

    <!-- jQuery library -->
    <script 
        src="https://code.jquery.com/jquery-git.js">
    </script>
</head>

<body>
    <p class="first">GeeksForGeeks</p>

    <p class="first">Hello Geeks</p>

    <script>

        // Class selector
        $(".first").css("color","blue")
    </script>
</body>

</html>
```

**输出:**

![](img/32710fa2b144a85ad9441e7c08ddcde3.png)

类别选择器

**让我们写一些代码，看看这些选择器实际上有多快？**

**示例:**我们将编写一个程序，该程序将使用不同的选择器执行相同的任务，让我们看看它们花费了多少时间。

## 超文本标记语言

```html
<!DOCTYPE html>

<head>
    <!-- jQuery library -->
    <script src=
        "https://code.jquery.com/jquery-git.js">
    </script>
</head>

<body>
    <p id="test">Hello</p>
    <p class="test">Hello</p>
    <h3>Hello</h3>

    <script>

        // ID Selector
        let id_time = Date.now();
        let id_t = 0;

        for (let i = 0; i < 100000; i++) {
            if ($("#test").css('background-color') == 'yellow')
                $("#test").css('background-color', 'red');
            else
                $("#test").css("background-color", "yellow");
        }

        id_t = Date.now() - id_time;
        console.log(' ID Selector : ' + id_t + ' milliseconds');

        /*-------------------------------------------------------*/

        // Class Selector
        let cl_time = Date.now();
        let cl_t = 0;

        for (i = 0; i < 100000; i++) {
            if ($(".test").css('background-color') == 'yellow')
                $(".test").css('background-color', 'red');
            else
                $(".test").css("background-color", "yellow");
        }

        cl_t = Date.now() - cl_time;

        console.log(' Class Selector :' + cl_t + ' milliseconds');

        /*----------------------------------------------------------*/

        // Element Selector
        let el_time = Date.now();
        let el_t = 0;

        for (i = 0; i < 100000; i++) {
            if ($("h3").css('background-color') == 'yellow')
                $("h3").css('background-color', 'red');
            else
                $("h3").css("background-color", "yellow");
        }

        el_t = Date.now() - el_time;
        console.log('Element Selector : ' + el_t + ' milliseconds');
    </script>
</body>

</html>
```

**输出:**

```html
ID Selector : 597 milliseconds
Class Selector :751 milliseconds
Element Selector : 741 milliseconds
```

看到上面代码的结果，很明显 ID 选择器是最快的。类和元素选择器花费的时间几乎相同。

**jQuery 中最快/最慢的选择器有哪些？**

在所有三个选择器中，ID 选择器是最快的选择器，因为任何 HTML 元素的 ID 在网页内都是唯一的，并且当加载网页时，浏览器将开始搜索具有指定 ID 的元素，并且 ID 是唯一的，因此当浏览器找到具有指定 ID 的元素时，它将停止搜索。

但是在类选择器的情况下，多个元素可以具有相同的类名，因此，浏览器必须遍历整个 DOM 来找出具有指定类名的每个元素。因此，类选择器被认为是最慢的选择器。

如果你在网页上有很多事情要做，而且不可能每次都使用一个 ID 选择器，那么最好的方法就是缓存。取出选择器一次，并保存起来以备将来使用。

**注意:**如果我们考虑今天的现代浏览器，那么这些选择器同样快速，因为在现代浏览器中，类名在内部被散列，我们有**。getElementsByClassName()** 而在旧的浏览器中没有类似于**的功能。getElementsByClassName()** 这就是原因**。类**名称在内部解析为 jQuery，然后遍历 DOM 的每个元素并检查类名。