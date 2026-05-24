# HTML | DOM ondragover 事件

> 原文:[https://www.geeksforgeeks.org/html-dom-ondragover-event/](https://www.geeksforgeeks.org/html-dom-ondragover-event/)

当一个可拖动的元素被拖动到一个有效的拖放区上时，就会发生 **HTML DOM ondragover 事件**。

**注意:**默认情况下，链接和图像是可拖动的。

拖放操作的不同阶段会使用和发生一些事件:

*   **ondragstart** :开始拖动元素时出现。*   **ondrag** :在元素拖动时发生。*   **ondragend**: occurs when dragging of an element finished.

    *   **ondragenter** :当被拖动元素进入放置目标时发生。
    *   **ondragover** :当被拖动的元素在放置目标上时发生。
    *   **软骨下**:当被拖动的元素从放置目标离开时发生。
    *   **ondrop** :当拖动的元素落在放置目标上时发生。

    **注意:**拖动元素时，ondragover 事件每 350 毫秒触发一次。

    **语法:**

    *   **在 HTML 中:**

        ```html
        <element ondragover="myScript">
        ```

    *   **在 JavaScript 中:**

        ```html
        object.ondragover = function(){myScript};
        ```

    *   **在 JavaScript 中，使用 addEventListener()方法:**

        ```html
        object.addEventListener("dragover", myScript);
        ```

    **示例:**使用 HTML。

    ```html
    <!DOCTYPE HTML>
    <html>

    <head>
        <style>
            #droptarget {
                float: center;
                width: 300px;
                height: 50px;
                margin: 20px;
                margin-top: 30px;
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
            <h2>
              HTML DOM ondragover Event
          </h2>
            <p ondragstart="dragStartEle(event)" 
               draggable="true" 
               id="dragtarget">
              Draggable element
          </p>

            <div id="droptarget" 
                 ondrop="dropEle(event)" 
                 ondragover="allowDropEle(event)">
            </div>

            <p id="try"></p>

            <script>
                function dragStartEle(event) {
                    event.dataTransfer.setData(
                      "Text", event.target.id);
                }

                function allowDropEle(event) {
                    event.preventDefault();
                    document.getElementById(
                      "try").innerHTML = 
                      "Element is over the dropzone";
                    event.target.style.border = "6px dotted green";
                }

                function dropEle(event) {
                    event.preventDefault();
                    var data = 
                        event.dataTransfer.getData("Text");

                    event.target.appendChild(
                      document.getElementById(data));

                    document.getElementById(
                      "try").innerHTML = "Dragging finished";
                }
            </script>
        </center>
    </body>

    </html>
    ```

    **输出:**
    ![](img/903712148d50babb731da86b3dc71d65.png)

    **示例:**使用 JavaScript

    ```html
    <!DOCTYPE HTML>
    <html>

    <head>
        <style>
            #droptarget {
                float: center;
                width: 300px;
                height: 50px;
                margin: 20px;
                margin-top: 30px;
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
            <h2>HTML DOM ondragover Event</h2>
            <p draggable="true" 
               id="dragtarget">
              Draggable element
          </p>

            <div id="droptarget"></div>

            <p id="demo"></p>

            <script>
                var drag = document.getElementById(
                  "dragtarget");
                var drop = document.getElementById(
                  "droptarget");

                // Events fired on the drag target 
                drag.ondragstart = function(event) {
                    event.dataTransfer.setData(
                      "Text", event.target.id);
                };

                drag.ondrag = function(event) {
                    document.getElementById(
                      "demo").innerHTML = 
                      "Dragging starts";
                };

                // Events fired on the drop target
                drop.ondragover = function(event) {
                    event.preventDefault();
                    document.getElementById(
                      "demo").innerHTML = 
                      "Element is over the dropzone";
                    event.target.style.border =
                      "6px dotted green";
                };

                drop.ondrop = function(event) {
                    event.preventDefault();
                    var data = 
                        event.dataTransfer.getData("Text");
                    event.target.appendChild(
                      document.getElementById(data));
                    document.getElementById(
                      "demo").innerHTML = "Dragging finished";
                };
            </script>
        </center>
    </body>

    </html>
    ```

    **输出:**
    ![](img/903712148d50babb731da86b3dc71d65.png)

    **示例:**使用 addEventListener()方法

    ```html
    <!DOCTYPE HTML>
    <html>

    <head>
        <style>
            #droptarget {
                float: center;
                width: 300px;
                height: 50px;
                margin: 20px;
                margin-top: 30px;
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
            <h2>HTML DOM ondragover Event</h2>
            <p draggable="true" id="dragtarget">
              Draggable element
          </p>

            <div id="droptarget"></div>

            <p id="try"></p>

            <script>
                var drag = document.getElementById(
                  "dragtarget");
                var drop = document.getElementById(
                  "droptarget");

                // Events fired on the drag target 

                drag.addEventListener(
                  "dragstart", function(event) {
                    event.dataTransfer.setData(
                      "Text", event.target.id);
                });

                drag.addEventListener(
                  "drag", function(event) {
                    document.getElementById(
                      "try").innerHTML = "Dragging starts";
                });

                // Events fired on the drop target 
                drop.addEventListener("dragover", function(event) {
                    event.preventDefault();
                    document.getElementById(
                      "try").innerHTML = "Element is over the dropzone";
                    event.target.style.border = "6px dotted green";
                });

                drop.addEventListener("drop", function(event) {
                    event.preventDefault();
                    var data = event.dataTransfer.getData("Text");

                    event.target.appendChild(
                      document.getElementById(data));

                    document.getElementById(
                      "try").innerHTML = "Dragging finished";
                });
            </script>
        </center>
    </body>

    </html>
    ```

    **输出:**
    ![](img/903712148d50babb731da86b3dc71d65.png)

    **支持的浏览器:****HTML DOM on dagover Event**支持的浏览器如下:

    *   谷歌 Chrome 4.0
    *   Internet Explorer 9.0
    *   Firefox 3.5
    *   苹果 Safari 6.0
    *   Opera 12.0