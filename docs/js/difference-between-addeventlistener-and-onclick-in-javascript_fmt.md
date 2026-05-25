# JavaScript 中 addEventListener 和 onclick 的区别

> 原文：[https://www.geeksforgeks.org/difference-between-addeventlistener-and-onclick-in-javascript/](https://www.geeksforgeks.org/difference-between-addeventlistener-and-onclick-in-javascript/)

`addEventListener()` 和 `onclick` 都在监听一个事件。两者都可以在单击按钮时执行回调函数。然而，它们并不相同。在本文中，我们将了解它们之间的差异。

## `addEventListener()`

[`addEventListener()`](https://www.geeksforgeks.org/javascript-addeventlistener-with-examples/) 方法将事件处理程序附加到指定的元素。

**语法：**

```
element.addEventListener(event, listener, useCapture);
```

**参数：**

*   `event`：事件可以是任何有效的 JavaScript 事件。使用不带“on”前缀的事件，如使用“click”而不是“onclick”或“mousedown”而不是“onmousedown”。
*   `listener`（处理函数）：它可以是一个响应发生的事件的 JavaScript 函数。
*   `useCapture`：（可选参数）一个布尔值，指定事件应该在捕获阶段还是在冒泡阶段执行。

**注意：** `addEventListener()` 方法可以对同一个元素应用多个事件处理程序。它不会覆盖其他事件处理程序。

**示例：** 下面是一个 JavaScript 代码，显示多个事件与一个元素相关联，并且没有覆盖。

### HTML 示例

```
<!DOCTYPE html>
<html>

<body>
    <button id="btn">Click here</button>
    <h1 id="text1"></h1>
    <h1 id="text2"></h1>

<script>
        let btn_element = document.getElementById("btn");

        btn_element.addEventListener("click", () => {
            document.getElementById("text1")
                .innerHTML = "Task 1 is performed";
        })

        btn_element.addEventListener("click", () => {
            document.getElementById("text2")
                .innerHTML = "Task 2 is performed";
        });
    </script>
</body>

</html>
```

**输出：**

![](img/54c7b281f153c37607f7b1a761cc255c.png)

## `onclick`

[`onclick`](https://www.geeksforgeeks.org/html-dom-onclick-event/) 事件属性在用户点击按钮时生效。当鼠标点击元素时，脚本运行。

**语法：**

**HTML 中：**

```
<element onclick="myScript">
```

**在 JavaScript 中：**

```
object.onclick = function(){myScript};
```

`onclick` 只是一个属性。像所有对象属性一样，如果我们编写多个属性，它将被覆盖。

**示例：** 下面是一个 JavaScript 代码，显示了多个事件不能与一个元素相关联，因为存在覆盖。

### HTML 示例

```
<!DOCTYPE html>
<html>

<body>
    <button id="btn">Click here</button>
    <h1 id="text1"></h1>
    <h1 id="text2"></h1>

<script>
        let btn_element = document.getElementById("btn");

        btn_element.onclick = () => {
            document.getElementById("text1")
                .innerHTML = "Task 1 is performed";
        };

        btn_element.onclick = () => {
            document.getElementById("text2")
                .innerHTML = "Task 2 is performed";
        };
    </script>
</body>

</html>
```

**输出：**

![](img/2a55cad4d070a55d0686c9e65a5d71de.png)

## `addEventListener` 与 `onclick` 的区别

| `addEventListener` | `onclick` |
| :--- | :--- |
| `addEventListener` 可以为特定元素添加多个事件。 | `onclick` 只能为元素添加单个事件。它本质上是一个属性，因此会被覆盖。 |
| `addEventListener` 可以接受第三个参数，该参数可以控制事件传播。 | `onclick` 无法控制事件传播。 |
| `addEventListener` 只能在元素内部或外部的 JavaScript 文件中添加。 | `onclick` 也可以作为 HTML 属性添加。 |
| `addEventListener` 在除 Internet Explorer 以外的所有现代浏览器中都有效。 | `onclick` 在所有浏览器中都有效。 |