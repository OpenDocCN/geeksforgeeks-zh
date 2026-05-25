# jQuery 中 hover() 和 mouseover() 方法的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-hover-and-mouseover-methods-in-jquery/](https://www.geeksforgeeks.org/difference-between-hover-and-mouseover-methods-in-jquery/)

在学习 jQuery 的 [`hover()`](https://www.geeksforgeeks.org/jquery-hover-with-examples/) 和 [`mouseover()`](https://www.geeksforgeeks.org/jquery-mouseover-with-examples/) 方法之间的区别之前，我们先简单看一下这两种方法。

**`hover()` 方法:** 当我们将鼠标光标悬停在任意元素上时，会发生两个事件，即 [`mouseenter`](https://www.geeksforgeeks.org/jquery-mouseenter-with-examples/) 和 [`mouseleave`](https://www.geeksforgeeks.org/jquery-mouseleave-with-examples/)。

*   **`mouseenter`:** 当我们将光标放在元素上时。
*   **`mouseleave`:** 当我们从元素中移除光标时。

`hover()` 方法绑定了 `mouseenter` 和 `mouseleave` 事件的处理程序。基本上，使用 `hover()` 方法，我们将指定当光标进入元素时要做什么，以及当光标离开该元素时要做什么。

**语法:**

```html
$( selector ).hover( handlerIn, handlerOut )
```

**参数:** 接受两个函数，即 `handlerIn` 和 `handlerOut`。

*   **`handlerIn`:** 当光标进入元素时会执行该函数。
*   **`handlerOut`:** (可选) 此函数在光标离开元素时执行。

当我们只提供一个函数作为 `hover()` 方法的参数时，该函数将为 `mouseenter` 和 `mouseleave` 事件执行。

**示例:** 在本例中，我们将看到如何使用 `hover()` 方法。我们有一个单词，每当光标进入元素时，我们都会尝试改变它的颜色。当光标离开该元素时，颜色将变回原来的颜色。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <!-- jQuery library -->
    <script src="https://code.jquery.com/jquery-git.js">
    </script>
</head>

<body>
    <h2>GeeksforGeeks</h2>

<script>
        // Calling hover() method 
        // on h1 tag
        $("h2").hover(
            // mouse-enter event
            function () {
                // changing the color
                $("h2").css('color', 'green')
            },
            // mouse-leave event
            function () {
                // Putting the color back
                $("h2").css('color', 'black')
            })
    </script>
</body>

</html>
```

**输出:**

![](img/8e9f24ccec71011139f98f5924f451ee.png)

**`mouseover()` 方法:** `mouseover()` 方法将在 `mouseover` 事件发生时执行。当光标进入元素时发生 `mouseover` 事件，然后将执行该元素的 `mouseover()` 方法。我们还可以附加一个函数，在调用 `mouseover()` 方法时执行。

**语法:**

```html
$(selector).mouseover(handler)
```

**参数:** (可选) 接受调用 `mouseover()` 方法时执行的函数。

**示例:** 在本例中，我们将看到如何使用 `mouseover()` 方法。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <!-- jQuery library -->
    <script src="https://code.jquery.com/jquery-git.js">
    </script>
</head>

<body>
    <h2>GeeksforGeeks</h2>

<script>
        $("h2").mouseover(
            function () {
                // changing the color
                $("h2").css('color', 'red')
            })
    </script>
</body>

</html>
```

**输出:**

![](img/675535dd09a7d62dedd336dfb32b4b30.png)

**`hover()` 和 `mouseover()` 方法的区别:**

| `hover()` | `mouseover()` |
| :--- | :--- |
| 绑定两个处理程序到匹配的元素，并在光标进入和退出元素时执行。 | 绑定一个处理程序到匹配的元素，并在光标进入元素时执行。 |
| 它最多接受两个函数作为参数，一个用于 `mouseenter` 事件，另一个用于 `mouseleave` 事件。 | 它最多接受一个函数作为参数，该函数将在 `mouseover` 事件发生时执行。 |
| 在 `hover()` 方法中，`handlerIn` 函数在光标进入元素或其子元素时被调用一次，`handlerOut` 函数在光标离开元素时被调用一次。 | 在 `mouseover()` 方法中，它的工作方式与 `hover()` 方法类似，但在嵌套元素的情况下，当光标进入附加了 `mouseover` 事件的外部元素时，会调用 `mouseover()` 方法，但当光标进入内部元素时，`mouseover()` 方法也会被调用。 |
| `handlerIn` 和 `handlerOut` 函数在每个元素进入和退出时都会被调用一次。 | 当元素嵌套时，此方法可能会被多次触发。 |