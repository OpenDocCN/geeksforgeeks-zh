# 如何使用 HTML CSS 和 JavaScript 创建滚动指示器？

> 原文:[https://www . geesforgeks . org/how-create-scroll-indicator-use-html-CSS-and-JavaScript/](https://www.geeksforgeeks.org/how-to-create-scroll-indicator-using-html-css-and-javascript/)

滚动指示器是一个进度条，表示页面滚动了多少。当我们向下滚动时，栏填满，当我们向上滚动时，栏的数量减少。

**方法:**现在，我们将创建一个带有文本的基本网页来启用滚动，然后使用 JavaScript 来使滚动指示器工作。

*   **HTML 代码:**在本节中，我们将创建身体的基本结构。

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <meta name="viewport" content=
            "width=device-width, initial-scale=1.0">
        <title>GFG : Scroll Indicator</title>
    </head>

    <body>
        <!--The scroll indicator line 
            at the top of page-->

        <div class="line" id="scrollIndicator"></div>

        <!--Content to fill the page 
            to enable scrolling-->
        <div class="text">
            <div>GeeksforGeeks</div>
            <div>GeeksforGeeks</div>
            <div>GeeksforGeeks</div>
            <div>GeeksforGeeks</div>
            <div>GeeksforGeeks</div>
            <div>GeeksforGeeks</div>
        </div>
    </body>

    </html>
    ```

*   **CSS code:** In this section, we will add some CSS property to set the style to create scroll indicator.

    ```html
    <style>
        body {
            margin: 0;
        }

        /* Formatting text to 
        fill the page */
        .text {
            font-size: 80px;
            color: green;
            text-align: center;
            line-height: 3em;
        }

        /* The progress bar - 
        scroll indicator */
        .line {
            background: green;
            height: 8px;
            border-radius: 4px;
            width: 0%;
            position: fixed;
            top: 0;
        }
    </style>
    ```

    **进场:**

    *   **window . inner height–**浏览器可视部分的高度。
    *   **document . body . scroll height–**网页的高度。
    *   **window . scrolly–**到目前为止用户向下滚动的像素数。
    *   **最大高度–**计算用户可以滚动的像素数。
    *   **百分比–**滚动指示器元素的宽度。
*   **JavaScript Code for Scroll Indicator:**

    ```html
    <script>

        // Added event listener to the scroll
        window.addEventListener('scroll',
                moveScrollIndicator);

        // Getting scrollIndicator element by ID
        const scrollIndicatorElt = 
            document.getElementById('scrollIndicator');

        // Height of entire web page - height
        // of viewable portion of browser
        const maxHeight = 
            window.document.body.scrollHeight 
            - window.innerHeight;

        function moveScrollIndicator(e) {

            // Calculating width of the 
            // scrollIndicator element
            const percentage = 
                ((window.scrollY) / maxHeight) * 100;

            // Pixels scrolled by the user 
            // to total scrollable Pixels
            scrollIndicatorElt.style.width
                     = percentage + '%';
        }
    </script>
    ```

    **完整代码:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>GFG : Scroll Indicator</title>
        <style>
            body {
                margin: 0;
            }

            .text {
                font-size: 80px;
                color: green;
                text-align: center;
                line-height: 3em;
            }

            .line {
                background: green;
                height: 8px;
                border-radius: 4px;
                width: 0%;
                position: fixed;
                top: 0;
            }
        </style>
    </head>

    <body>
        <div class="line" id="scrollIndicator"></div>

        <div class="text">
            <div>GeeksforGeeks</div>
            <div>GeeksforGeeks</div>
            <div>GeeksforGeeks</div>
            <div>GeeksforGeeks</div>
            <div>GeeksforGeeks</div>
            <div>GeeksforGeeks</div>
        </div>

        <script type="text/javascript">
            window.addEventListener('scroll',
                    moveScrollIndicator);

            const scrollIndicatorElt =
                document.getElementById('scrollIndicator');

            const maxHeight =
                window.document.body.scrollHeight
                - window.innerHeight;

            function moveScrollIndicator(e) {
                const percentage = 
                    ((window.scrollY) / maxHeight) * 100;

                scrollIndicatorElt.style.width
                    = percentage + '%';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**
    ![Scroll Indicator Working](img/fed7b466ca551661844df9d15e6af61e.png)