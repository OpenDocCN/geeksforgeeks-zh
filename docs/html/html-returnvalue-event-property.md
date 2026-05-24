# HTML |返回值事件属性

> 原文:[https://www . geesforgeks . org/html-return value-event-property/](https://www.geeksforgeeks.org/html-returnvalue-event-property/)

它可以**设置**或**检索**一个布尔值，该值告诉*当前事件是否被取消*。**返回值事件属性**告知该事件的默认操作是否被阻止。默认情况下，该值设置为 true，它允许发生默认操作。
如果我们将默认值设置为 false，它将阻止默认操作。

**语法:**

```html
event.returnValue = bool;
var booleanValue = event.returnValue;
```

**返回值:**
如果事件没有被取消，则返回值为真，如果事件被取消或默认被阻止，则返回值为假。

**示例 1:** 本示例试图取消 onclick 和 onchange 事件。

```html
<!DOCTYPE html>
<html>

<head>
    <title>returnValue event property</title>
    <style>
        h1 {
            color: green;
        }

        div {
            width: 500px;
            height: 200px;
            overflow: auto;
            border: 1px solid green;
        }
    </style>

</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <script type="text/javascript">
            function WriteInformation(message) {
                var inform = document.getElementById("info");
                inform.innerHTML += message + "<br />";
                inform.scrollTop = inform.scrollHeight;
            }

            function CancelEvent(event, NameEvent) {
                if ('cancelable' in event) {
                   if (event.cancelable) {
                        event.preventDefault();
                        WriteInformation(
                          "The " + NameEvent + 
                          " event is canceled.");
                    } else {
                        WriteInformation(
                          "The " + NameEvent +
                          " event is not cancelable.");
                    }
                } else {
                    event.returnValue = false;
                    WriteInformation(
                      "The " + NameEvent +
                      " event is probably canceled.");
                }
            }
        </script>
        <input type="checkbox" 
               onclick="CancelEvent (event, 'onclick');" />
      Try to check this checkbox.
        <br />
        <br /> Select one of the one options.
        <select onchange="CancelEvent (event, 'onchange');">
            <option>Option 1</option>
            <option>Option2</option>
        </select>
        <br />
        <br />

        <div id="info" style=""></div>
    </center>
</body>

</HTML>
```

**输出:**
[![](https://cdn1.imggmi.com/uploads/2019/5/16/7b41aa290934b596d8f23040a92acff7-full.png)](https://imggmi.com)

**示例 2:** 与上一个示例类似，不同的是它不检查事件的可取消状态，它只是尝试取消 onclick 和 onchange 事件。

```html
<!DOCTYPE html>
<html>

<head>
    <title>returnValue event property</title>
    <style>
        h1 {
            color: green;
        }        
        body {
            text-align: center;
        }
    </style>

</head>

<body>
    <h1>GeeksforGeeks</h1>
    <script type="text/javascript">
        function WriteInformation(message) {
            var inform = document.getElementById("info");
            inform.innerHTML += message + "<br />";
            inform.scrollTop = inform.scrollHeight;
        }

        function CancelEvent(event, NameEvent) {
            if ('cancelable' in event) {
                if (event.cancelable) {
                    event.preventDefault();
                    WriteInformation(
                      "The " + NameEvent + 
                      " event is canceled");
                } else {
                    WriteInformation(
                      "The " + NameEvent +
                      " event is not cancelable");
                }
            } else {
                event.returnValue = false;
                WriteInformation(
                  "The " + eventName + 
                  " event is maybe canceled");
            }
        }
    </script>
    In this it cancels the onclick event for the checkbox
    <br /> and the onchange event for the selection list below.
    <br /> The onclick event is cancelable, the onchange is not.
    <br />
    <br />
    <input type="checkbox" 
           onclick="return false;" /> 
  Try to check this checkbox.
    <br />
    <br /> Select one of the one options.
    <select onchange="return false;">
        <option>First option</option>
        <option>Second option</option>
    </select>
</body>

</HTML>
```

**输出:**
[![](https://cdn1.imggmi.com/uploads/2019/5/16/6efc9c424608bff92e2165309d3d79c8-full.png)](https://imggmi.com)

**支持的浏览器:**

*   谷歌 Chrome
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari