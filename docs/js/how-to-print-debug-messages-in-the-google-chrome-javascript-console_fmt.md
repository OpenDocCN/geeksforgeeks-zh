# 如何在谷歌 Chrome JavaScript 控制台打印调试消息？

> 原文：[https://www.geeksforgeeks.org/how-to-print-debug-messages-in-the-google-chrome-javascript-console/](https://www.geeksforgeeks.org/how-to-print-debug-messages-in-the-google-chrome-javascript-console/)

在控制台中打印非常容易，我们只需要知道如何激活 chrome 上的控制台进行查看。控制台总是活动的，我们所做的就是让它对前端可见。`console`对象是提供对浏览器调试控制台的访问的对象。`Console`对象有很多方法可以帮助我们打印定制调试。

## 控制台方法

以下是一些方法：

*   `assert()`: 行为类似“if”，如果为 false 则打印到控制台。
*   `clear()`: 清除控制台。
*   `count()`: 每当被调用时都会计数。
*   `error()`: 打印错误(如果有)。
*   `group()`: 在控制台中创建新的内联组。
*   `groupCollapsed()`: 在控制台中创建新的内联折叠组。
*   `groupEnd()`: 退出控制台中的内联组。
*   `info()`: 只是作为日志，用于优先级信息。
*   `log()`: 向控制台输出消息。
*   `table()`: 将表格数据显示为表格。
*   `time()`: 跟踪特定任务发生的时间。
*   `timeEnd()`: 结束追踪器。
*   `trace()`: 输出堆栈跟踪。
*   `warn()`: 输出警告信息。

> 运行脚本后，单击 F12，它将打开开发人员工具，导航到控制台选项卡，该选项卡将位于顶部菜单上。

## 示例 1

```html
<!DOCTYPE html>
<html>

<body>

<h2>Debugging in Console</h2>

<p>On Clicking the below button,
      myFunction() invokes and prints in the console.</p>
    <input type="button"
           onclick="myFunction()"
           value="Tony send signal to Quill(console)">
    <!--button-->
    <script>
        function myFunction() {
            //prints in console
            console.log("log:Tony sent a message");

            //prints in console
            console.info("info:Quill recieved."); 
        }
    </script>

</body>

</html>
```

**输出:**

**前:**

[![output](img/d06ee022a8f70150f9974cfb284c3f33.png)](https://contribute.geeksforgeeks.org/?attachment_id=1270379)

输出 1

**点击按钮后:**

[![output](img/23c9567990977b91af643528a0ee5b54.png)](https://contribute.geeksforgeeks.org/?attachment_id=1270380)

输出 2

## 示例 2

查看 `console.table()` 以更好地理解方法。

```html
<!DOCTYPE html>
<html>

<body>

<h2>Debugging in Console</h2>

<p>On Clicking the below button, 
      myFunction() invokes and prints in the console.</p>
    <input type="button" 
           onclick="myFunction()" 
           value="who are the guardians?">
    <script>
        function myFunction() {
            console.table(["Quill", "Gamora", "Drax",
                           "Groot", "Rocket", "mantis"]);
        }
    </script>

</body>

</html>
```

**输出**

**前:**

[![output](img/7bba27f97ebcd4edf6a6d3f98778dd6f.png)](https://contribute.geeksforgeeks.org/?attachment_id=1270397)

输出 1

**点击按钮后:**

[![output](img/1e5082321f7e899b8836e18d8d1d1ec7.png)](https://contribute.geeksforgeeks.org/?attachment_id=1270398)

输出 2