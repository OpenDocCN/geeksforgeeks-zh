# jQuery | event.target 属性示例

> 原文:[https://www . geeksforgeeks . org/jquery-event-target-property-with-example/](https://www.geeksforgeeks.org/jquery-event-target-property-with-example/)

**事件目标**是 jQuery 中的一个内置属性，用于查找哪个 DOM 元素将启动该事件。
**语法:**

```html
event.target

```

**参数:**它不接受任何参数，因为它是属性而不是函数。
**返回值:**返回触发事件的 DOM 元素。

**显示事件工作的 jQuery 代码. target Property 属性:**

```html
<html>

<head>
    <style>
        span,
        strong,
        p {
            padding: 8px;
            display: block;
            border: 2px solid green;
            width: 50%;
            margin: 10px;
        }

        #output {
            margin: 10px;
            padding: 10px;
            width: 100px;
            border: 2px solid green;
            display: block;
        }
    </style>
    <script src="https://code.jquery.com/jquery-1.10.2.js">
    </script>
</head>

<body>
    <div>
        <p>
            <strong><span>click Here !</span></strong>
        </p>
    </div>
    <!-- output will show inside this block -->
    <div id="output"></div>
    <!-- jQuery code to show working of this property -->
    <script>
        $("body").click(function(event) {
            $("#output").html("clicked: " + event.target.nodeName);
        });
    </script>
</body>

</html>
```

**输出:**
点击任意位置前-
![](img/263813ca72ccd91cba9829c5ea32adbb.png)

点击 p 元素内部后-
![](img/98052af7682759db08c6528246d9c122.png)

点击强元素内部后-
![](img/63a53c7c5bebaeda6b1b75ee2e0f9fe5.png)

点击 SPAN 元素内部后-
![](img/98ef6d2880c5d40c38d8769905fed17b.png)