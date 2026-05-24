# 解释 jQuery

中 animate()方法的用途

> 原文:[https://www . geesforgeks . org/explain-目的-动画-方法-in-jquery/](https://www.geeksforgeeks.org/explain-the-purpose-of-animate-method-in-jquery/)

然后 jQuery 中可用的 [animate()](https://www.geeksforgeeks.org/jquery-animate-with-examples/) 方法可以用来为我们的网页创建一个交互式 UI。我们使用**动画()**方法来执行一组 CSS 属性的自定义动画。

**animate()** 方法将无法动画化字符串值，例如，我们无法动画化“背景色”和类似常规 jQuery 中的属性。我们将只能激活单个数值。比如*身高、体重、边距、填充*等。

在本文中，我们将看到各种场景，在这些场景中，我们可以实际使用 **animate()** 方法。

**语法:**

```html
.animate( <css properties>, duration, easing, callback)
```

*   **CSS 属性:**高度、重量、边距、填充等(具有单个数值的属性)。
*   **持续时间:**它将是一个字符串或数字，将决定动画将运行多长时间。
*   **回调:**是动画结束时可以调用的函数。

我们将看到一些用*创建的例子。动画*方法并在我们的项目中使用。

**示例 1:** 以下示例在悬停时为搜索栏设置动画。我们将创建一个正常大小的搜索栏，但是当我们将鼠标悬停时，搜索栏的宽度将会扩大。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>

    <style>
        * {
            margin: 0px;
            padding: 0px;
            box-sizing: border-box;
        }

        body {
            background-color: rgb(34, 34, 34);
        }

        #Container {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            color: white;
            font-family: -apple-system, BlinkMacSystemFont, 
                "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, 
                "Open Sans", "Helvetica Neue", sans-serif;
        }

        #t1 {
            margin: 20px;
            padding-left: 10px;
            font-size: 20px;
            text-align: center;
            width: 50px;
            height: 50px;
            border: none;
            background-color: floralwhite;
            background-image: url(
"https://media.geeksforgeeks.org/wp-content/uploads/20210816221058/searchIcon.png");
            background-size: 30px 30px;
            background-repeat: no-repeat;
            background-position: 50%;
            border-radius: 50%;
            outline: none;
        }
    </style>
</head>

<body>
    <div id="Container">
        <h3>SEARCH</h3>
        <input type="text" id="t1" />
    </div>

    <script>
        $(document).ready(function() {
            $("#t1").mouseover(function() {
                $("#t1").animate({
                    width: "200px",
                    borderRadius: "50px",
                    backgroundSize: "0px",
                });
            });

            $("#t1").mouseout(function() {
                $("#t1").animate({
                    width: "50px",
                    borderRadius: "50px",
                    backgroundSize: "30px",
                });
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/f66368ea11d82873c8ca8f5eb85397cb.png)

**示例 2:** 以下代码演示了使用不透明度值制作加载屏幕的动画。在这个例子中，我们将创建一个加载文本，它将被不透明度动画化，以获得它仍然在加载的感觉。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>

    <style>
        * {
            margin: 0px;
            padding: 0px;
            box-sizing: border-box;
        }

        body {
            background-color: rgb(34, 34, 34);
        }

        #Container {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            color: white;
            font-family: -apple-system, BlinkMacSystemFont,
                "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, 
                "Open Sans", "Helvetica Neue", sans-serif;
        }

        .loading {
            height: 50px;
            width: 200px;
            background-color: rgb(0, 0, 0);
            color: green;
            font-size: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 8px;
        }
    </style>
</head>

<body>
    <div id="Container">
        <div class="loading">
            Loading...
        </div>
    </div>

    <script>
        $(document).ready(function() {
            var div = $(".loading");
            div.animate({
                opacity: '0.5'
            }, "slow");
            div.animate({
                opacity: '0.9'
            }, "slow");
            div.animate({
                opacity: '0.5'
            }, "slow");
            div.animate({
                opacity: '0.9'
            }, "slow");
            div.animate({
                opacity: '0.5'
            }, "slow");
            div.animate({
                opacity: '0.9'
            }, "slow");
        });
    </script>
</body>

</html>
```

**输出:**

![](img/b3a42af6611d72ec74ad9be6341a50b4.png)