# 如何检查 jQuery 中是否使用了事件命名空间？

> 原文:[https://www . geesforgeks . org/how-to-check-event-namespace-in-jquery/](https://www.geeksforgeeks.org/how-to-check-whether-the-event-namespace-is-used-in-jquery/)

jQuery 是轻量级的，它有很多特性，比如 HTML/DOM 操作、CSS 操作、HTML 事件方法、效果和动画、AJAX、实用程序。许多跨国公司，如谷歌、IBM 和微软，在其应用程序中使用 jQuery 库。

当事件被触发时， [*事件.命名空间*](https://www.geeksforgeeks.org/jquery-event-namespace-property/) 属性返回自定义命名空间。该属性将主要由插件作者使用，他们希望根据所使用的事件名称空间以不同的方式处理任务。

**示例:**下面是用于确定使用的事件命名空间的 HTML 代码。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8" />
    <script src=
        "https://code.jquery.com/jquery-3.5.0.js">
    </script>
</head>

<body>
    <h2 style="color: green">GeeksforGeeks</h2>
    <button>Click here</button>
    <div style="height: 10px"></div>
    <div id="showEventNamespace"></div>

    <script>

        // Attach one or more event using .on() method
        $("#showEventNamespace").on(
            "test.GeeksForGeeksEventNamespace",
            function (event) {

                // event.namespace message is
                // shown in the div
                $("#showEventNamespace").show()
                    .html(event.namespace);
            }
        );

        // On click of the button, the event
        // namespace is triggered
        $("button").click(function (event) {
            $("#showEventNamespace")
                .trigger("test.GeeksForGeeksEventNamespace");
        });
    </script>
</body>

</html>
```

**输出:**

![](img/29b8bfbb8784508dfc81b82d4d28e789.png)

event.namespace

**注意:**以下划线开头的命名空间是为 jQuery 保留的。