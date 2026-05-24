# jQuery 中悬停()和鼠标悬停()方法的区别

> 原文:[https://www . geesforgeks . org/hover-and-mouse-over-methods-in-jquery/](https://www.geeksforgeeks.org/difference-between-hover-and-mouseover-methods-in-jquery/)

在学习 jQuery 的 [**悬停()**](https://www.geeksforgeeks.org/jquery-hover-with-examples/) 和 [**鼠标悬停()**](https://www.geeksforgeeks.org/jquery-mouseover-with-examples/) 方法之间的区别之前，我们先简单看一下这两种方法。

**悬停()方法:**当我们将鼠标光标悬停在任意元素上时，会发生两个事件，即[](https://www.geeksforgeeks.org/jquery-mouseenter-with-examples/)****r**和[**mouse leave**](https://www.geeksforgeeks.org/jquery-mouseleave-with-examples/)**。****

*   ****鼠标输入:**当我们将光标放在元素上时。**
*   ****mouseleave:** 当我们从元素中移除光标时。**

****悬停()**方法绑定了**鼠标进入**和**鼠标离开**事件的处理程序。基本上，使用**悬停()**方法，我们将指定当光标进入元素时要做什么，以及当光标离开该元素时要做什么。**

****语法:****

```html
$( selector ).hover( handlerIn, handlerOut )
```

****参数:**接受两个功能，即 handlerIn 和 handlerOut。**

*   ****handlerIn:** 当光标进入元素时会执行该功能。**
*   ****handlerOut:** (可选)此功能在光标离开元素时执行。**

**当我们只提供一个函数作为**悬停()**方法的参数时，该函数将为**鼠标进入**和**鼠标离开**事件执行。**

****示例:**在本例中，我们将看到如何使用**悬停()**方法。我们有一个单词，每当光标进入元素时，我们都会尝试改变它的颜色。当光标离开该元素时，颜色将变回原来的颜色。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html>

<head>
    <!-- jQuery library -->
    <script src=
"https://code.jquery.com/jquery-git.js">
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

****输出:****

**![](img/8e9f24ccec71011139f98f5924f451ee.png)

悬停方法** 

****鼠标悬停()方法:****鼠标悬停()**方法将在**鼠标悬停**事件发生时执行。当光标进入元素时发生**鼠标悬停**事件，然后将执行该元素的**鼠标悬停()**方法。我们还可以附加一个函数，在调用 **mouseover()** 方法时执行。**

****语法:****

```html
$(selector).mouseover(handler)
```

****参数:**(可选)接受调用**鼠标悬停()**方法时执行的函数。**

****示例:**在本例中，我们将看到如何使用 mouseover()方法。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html>

<head>
    <!-- jQuery library -->
    <script src=
    "https://code.jquery.com/jquery-git.js">
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

****输出:****

**![](img/675535dd09a7d62dedd336dfb32b4b30.png)**

****hover()和 mouseover()方法的区别:****

<figure class="table">

| 

hover()

 | 

mouse over()

 |
| --- | --- |
| Bind two handlers to the matching elements and execute when the cursor enters and exits the elements. | Bind a handler to the matching element and execute it when the cursor enters the element. |
| It accepts at most two functions as parameters, one for **mouse entering** event and the other for **mouse leaving** event. | It accepts at most one function as a parameter, which will be executed when the **mouse hovers over the** event. |
| In the **hover ()** method, the **handlerin** function is called once when the cursor enters the element or its child elements, and the **handleout** function is called once when the cursor leaves the element. | In the **mouseover ()** method <u>, I</u> t works in the same way as the **hover ()** method, but in the case of nested elements, when the cursor enters the outside with mouseover event attached, the mouseover () method will be called, but when the cursor enters the inside, mouseover ( |
| HandlerIn and handlerOut functions will be called once every time each element enters and exits. | This method can be fired multiple times when elements are nested. |

</figure>