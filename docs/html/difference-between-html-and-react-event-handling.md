# 【HTML 和 React 事件处理的区别

> 原文:[https://www . geesforgeks . org/html 和 react 之间的差异-事件处理/](https://www.geeksforgeeks.org/difference-between-html-and-react-event-handling/)

HTML 和 React 中的事件处理在语法和一些规则方面彼此不同。这背后的原因是 React 工作在虚拟 DOM 的概念上，另一方面，HTML 一直可以访问真实的 DOM。我们将看到如何在 HTML 中添加事件，以及 React 在事件处理中有何不同。

**在 HTML** 中，我们是直接为 Real DOM 编写代码，所以为了 Real DOM 让知道我们指的是 javascript 函数或方法，我们需要在字符串的末尾指定“()”。如果我们不想采用这种方法，还有一种使用 javascript 的方法。我们需要使用 addEventLisener 来指定事件和侦听器。

这两种方法都运行良好，我们使用第一种方法进行了一次 onclick，使用 addEventlistener 进行了一次 onclick，这两种方法都在用户单击时向用户致意。如您所见，第一个按钮没有任何 id，我们使用第一个方法“onclick”来指定事件。很明显，我们提供了字符串形式的“greet()”，并在末尾提供了括号(参见第一个脚本标签)。第二个方法是使用 addEventListener，我们已经指定了事件“Click”并给出了回调，我们还可以给出方法名。参见[本](https://www.geeksforgeeks.org/javascript-addeventlistener-with-examples/)篇。

**例:**

## index.htm

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />

    <style>
        .btn {
            padding: 20px;
            background-color: blueviolet;
            color: white;
            font-size: 20px;
        }
    </style>
    <!-- script for onclick method -->
    <script>
        var greet = function () {
            window.alert("hello onclick event sent me");
        };
    </script>
</head>

<body>
    <button class="btn" onclick="greet()">
        Greet me using "onclick"
    </button>

    <button id="b1" class="btn">
        Greet me using addEventListener
    </button>

    <!-- Script for addevnetListner -->
    <script>
        var button = document.getElementById("b1");
        button.addEventListener("click", () =>
            window.alert("hello addevnetlistner sent me")
        );
    </script>
</body>

</html>
```