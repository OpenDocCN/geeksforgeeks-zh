# html \ DOM 处理程序事件

> 原文:[https://www.geeksforgeeks.org/html-dom-ondragenter-event/](https://www.geeksforgeeks.org/html-dom-ondragenter-event/)

当可拖动元素进入有效的放置目标时，就会发生**事件。
ondragenter 和 ondragleave 事件可以帮助用户理解 dropzone。
在拖放操作的不同阶段使用和发生了一些事件:** 

*   **ondragstart:** 在开始拖动元素时出现。
*   **ondrag:** 在元素拖动时发生。
*   **ondragend:** 在元素拖动完成时出现。

*   **ondragenter:** 当被拖动的元素进入放置目标时发生。
*   **ondragover:** 当被拖动的元素在放置目标上时发生。
*   **软骨上:**当被拖动的元素从放置目标离开时发生。
*   **ondrop:** 当拖动的元素放在放置目标上时发生。

**支持的标签:**支持所有 HTML 元素。

**语法:**

*   **在 HTML 中:**

```html
<element ondragenter="myScript">
```

*   **在 JavaScript 中:**

```html
object.ondragenter = function(){myScript};
```

*   **在 JavaScript 中，使用 addEventListener()方法:**

```html
object.addEventListener("dragenter", myScript);
```

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>
      HTML DOM ondrop Event
  </title>
    <style>
        .droptarget {
            float: center;
            width: 300px;
            height: 50px;
            margin: 20px;
            padding: 5px;
            border: 6px solid green;
        }
    </style>
</head>

<body>
    <center>
        <h1 style="color:green">
        GeeksforGeeks
    </h1>
        <h2>HTML DOM ondrop Event</h2>

        <div class="droptarget"
             ondrop="Eledrop(event)"
             ondragenter="EledragEnter(event)"
             ondragleave="EledragLeave(event)"
             ondragover="EleallowDrop(event)">

            <p ondragstart="EledragStart(event)"
               draggable="true"
               id="dragtarget">
                Dragable element
            </p>

        </div>

        <div class="droptarget"
             ondragenter="EledragEnter(event)"
             ondragleave="EledragLeave(event)"
             ondrop="Eledrop(event)"
             ondragover="EleallowDrop(event)">
        </div>

        <p id="demo"></p>

        <script>
            function EledragStart(event) {
                event.dataTransfer.setData("Text", event.target.id);
            }

            function EledragEnter(event) {
                if (event.target.className == "droptarget") {
                    document.getElementById(
                      "demo").innerHTML = "Entered the dropzone";
                    event.target.style.border = "6px dotted red";
                }
            }

            function EledragLeave(event) {
                if (event.target.className == "droptarget") {
                    document.getElementById(
                      "demo").innerHTML = "Left the dropzone";
                    event.target.style.border = "";
                }
            }

            function EleallowDrop(event) {
                event.preventDefault();
            }

            function Eledrop(event) {
                event.preventDefault();
                var data = event.dataTransfer.getData("Text");
                event.target.appendChild(document.getElementById(data));
            }
        </script>
  </center>
</body>

</html>
```

**输出:**

![](img/5264674c6671ccb956b3548a8b8bc0b2.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>
        HTML DOM ondrop Event
    </title>
    <style>
        .droptarget {
            float: center;
            width: 300px;
            height: 50px;
            margin: 20px;
            padding: 5px;
            border: 6px solid green;
        }
    </style>
</head>

<body>
    <center>
        <h1 style="color:green">
        GeeksforGeeks
    </h1>
        <h2>HTML DOM ondrop Event</h2>

        <div class="droptarget">
            <p draggable="true"
               id="dragtarget">
                Draggable Element
            </p>

        </div>

        <div class="droptarget"></div>

        <p id="demo"></p>

        <script>
            // Event fired on the drag target
            document.ondragstart = function(event) {
                event.dataTransfer.setData("Text", event.target.id);
            };

            // Events fired on the drop target
            document.ondragenter = function(event) {
                if (event.target.className == "droptarget") {
                    document.getElementById(
                      "demo").innerHTML = "Entered the dropzone";
                    event.target.style.backgroundColor = "yellow";
                }
            };

            document.ondragover = function(event) {
                event.preventDefault();
            };

            document.ondragleave = function(event) {
                if (event.target.className == "droptarget") {
                    document.getElementById(
                      "demo").innerHTML = "Left the dropzone";
                    event.target.style.backgroundColor = "";
                }
            };

            document.ondrop = function(event) {
                event.preventDefault();
                if (event.target.className == "droptarget") {
                    event.target.style.backgroundColor = "";
                    var data = event.dataTransfer.getData("Text");
                    event.target.appendChild(document.getElementById(data));
                }
            };
        </script>
    </center>

</body>

</html>
```

**输出:**

![](img/715724ac51c67918b4ed689bfcfc09f6.png)

**例 3:**

## 超文本标记语言

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>HTML DOM ondrop Event</title>
    <style>
        .droptarget {
            float: center;
            width: 300px;
            height: 50px;
            margin: 20px;
            padding: 5px;
            border: 6px solid green;
        }
    </style>
</head>

<body>
    <center>
        <h1 style="color:green">
        GeeksforGeeks
    </h1>
        <h2>HTML DOM ondrop Event</h2>

        <div class="droptarget">
            <p draggable="true"
               id="dragtarget">
                Draggable Element
            </p>

        </div>

        <div class="droptarget"></div>

        <p id="demo"></p>

        <script>
            document.addEventListener("dragstart", function(event) {
                event.dataTransfer.setData("Text", event.target.id);
            });

            document.addEventListener("dragenter", function(event) {
                if (event.target.className == "droptarget") {
                    document.getElementById("demo").innerHTML =
                        "Entered the dropzone";
                    event.target.style.backgroundColor = "yellow";
                }
            });

            document.addEventListener("dragover", function(event) {
                event.preventDefault();
            });

            document.addEventListener("dragleave", function(event) {
                if (event.target.className == "droptarget") {
                    document.getElementById(
                      "demo").innerHTML = "Left the dropzone";
                    event.target.style.backgroundColor = "";
                }
            });

            document.addEventListener("drop", function(event) {
                event.preventDefault();
                if (event.target.className == "droptarget") {
                    event.target.style.backgroundColor = "";
                    var data = event.dataTransfer.getData("Text");
                    event.target.appendChild(document.getElementById(data));
                }
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/ffde5deb381db2073843cc730c7faef2.png)

**支持的浏览器:****ondragenter 事件**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧