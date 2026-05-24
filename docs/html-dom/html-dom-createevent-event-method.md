# HTML | DOM createEvent()事件方法

> 原文:[https://www . geesforgeks . org/html-DOM-createevent-event-method/](https://www.geeksforgeeks.org/html-dom-createevent-event-method/)

HTML 中的 c**createevent()**方法创建一个指定类型的事件对象。创建的事件必须在使用前初始化。

**语法:**

```html
document.createEvent( event_type )
```

**事件 _ 类型:**为必选项，用于指定事件的类型。

下面列出了许多类型的事件:

*   动画事件
*   剪贴板事件
*   德拉戈事件
*   聚焦事件
*   HashChangeEvent
*   输入事件
*   键盘事件
*   老鼠事件

*   页面传输事件
*   PopStateEvent
*   ProgressEvent
*   StorageEvent
*   TouchEvent(触地事件)
*   TransitionEvent
*   UiEvent(事件)
*   WheelEvent

下面的程序用 HTML 说明了 createEvent()方法:

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            DOM createEvent() Event Method
        </title>

        <style>
            div {
                padding:50px;
                text-align:center;
                background-color: green;
                color: white;
            }
        </style>
    </head>

    <body>
        <script>
            document.body.onclick = function() {
                document.getElementById("Geeks").innerHTML 
                            = "Welcome to GeeksforGeeks!";
            };

            var onClick = function() {
                var evt = document.createEvent("MouseEvents");
                evt.initMouseEvent
                    ("click", true, true, window, 0, 0, 0, 0,
                    0, false, false, false, false, 0, null);
                document.body.dispatchEvent(evt);
            }

            onClick();
        </script>

        <div id = "Geeks"></div>

    </body>
</html>                    
```

**输出:**
**前点击元素:**
![](img/54943013c0fede9322aaa08065cae0b5.png)
**后点击元素:**
![](img/5c0443aaeb0cf3e795c7ddd4099efa04.png)

**支持的浏览器:**T2 DOM createEvent()方法支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队