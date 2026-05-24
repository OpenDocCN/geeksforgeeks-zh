# 如何使用 HTML、CSS 和 JavaScript 创建二进制计算器？

> 原文:[https://www . geesforgeks . org/如何使用 html-CSS-和-javascript 创建二进制计算器/](https://www.geeksforgeeks.org/how-to-create-a-binary-calculator-using-html-css-and-javascript/)

HTML 或超文本标记语言以及 CSS(级联样式表)和 JavaScript 可以用来开发交互式用户应用程序，这些应用程序可以执行某些功能。同样，可以使用 HTML、CSS 和 JS 开发二进制计算器。二进制计算器对二进制数执行算术运算。二进制计算器的缓冲区限制为 8 位。如果算术运算的结果超过 8 位，则多余的位被截断。算术运算是使用 JavaScript 函数完成的。该应用程序由显示屏组成，用户输入和算术运算的结果都显示在该显示屏上。两个按钮 0 和 1 用于输入。+、–、*和/计算按钮用于对输入进行算术运算。计算按钮与 JavaScript 函数 Calculate()绑定在一起。单击计算按钮时，将触发计算()函数，并解析“输出”部分中的 HTML。第一个数字和第二个数字是通过拆分字符串获得的，最后，使用 parseInt()将它们转换为整数。parseInt()方法接受两个参数，其中第一个参数是要转换为整数的字符串，第二个参数是基值，在本例中为 2 或二进制。算术运算的执行取决于用户选择的加法、减法、乘法或除法运算符。input()函数接收用户的输入，并将其显示在屏幕上。函数的作用是:删除显示的字符串的最后一个字符。cls()函数清除显示屏。下面的代码片段实现了一个二进制计算器。

**示例:**当用户给出输入时，输入以 HTML 的形式保留在‘输出’部分。声明了一个全局变量 scr，所有的 JavaScript 函数都可以访问它。当任何输入被给出时，它被存储在 scr 变量中。单击“计算”按钮时，将使用 indexOf()方法搜索存储在 scr 变量中的字符串是否存在运算符，如果找到，则返回运算符的索引，否则返回-1。如果运算符存在，存储在 scr 变量中的字符串将在运算符符号(+、-、*、/)处拆分，并将字符串存储到 num 数组中。由于输入是字符串格式，因此必须将其转换为二进制整数格式才能执行计算。使用 parseint(str，base)方法解析字符串，其中 str 是要转换的字符串，base 是数字的基数(此处为二进制基数= 2)。二进制转换后，执行指定的算术运算，结果再次存储在 scr 变量中，并显示在“输出”部分。

1.  **HTML:**

    ## 超文本标记语言

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="utf-8" />
            <title>Binary Calculator</title>

            <!--Bootstrap 4 CSS CDN -->
            <link rel="stylesheet" 
                  href=
    "https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" 
                  integrity=
    "sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" 
                  crossorigin="anonymous" />
        </head>

        <body>
            <div class="container">
                <div class="jumbotron">
                    <h1>Binary Calculator</h1>
                    <div id="output"></div>
                    <div class="container mt-2">
                        <div class="row">
                            <div class="col-12">
                                <button type="button" 
                                        class="btn btn-light" 
                                        onclick="input('0')">
                                          0</button>
                                <button type="button" 
                                        class="btn btn-light" 
                                        onclick="input('1')">
                                          1</button>
                                <button type="button" 
                                        class="btn btn-danger float-right ml-2" 
                                        onclick="cls()">
                                          AC</button>
                                <button type="button" 
                                        class="btn btn-warning float-right" 
                                        onclick="backspace()">
                                          Backspace</button>
                            </div>
                        </div>
                        <div class="row mt-2">
                            <div class="col-12">
                                <button type="button" 
                                        class="btn btn-info" 
                                        onclick="input('+')">+</button>
                                <button type="button"
                                        class="btn btn-info" 
                                        onclick="input('-')">-</button>
                                <button type="button" 
                                        class="btn btn-info" 
                                        onclick="input('*')">*</button>
                                <button type="button" 
                                        class="btn btn-info" 
                                        onclick="input('/')">/</button>
                            </div>
                        </div>
                        <div class="row mt-2">
                            <div class="col-12">
                                <button type="button" 
                                        class="btn btn-success" 
                                        onclick="calculate()">Calculate</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <!--jquery and popper.js cdn -->
            <script src=
    "https://code.jquery.com/jquery-3.5.1.slim.min.js" 
                    integrity=
    "sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" 
                    crossorigin="anonymous"></script>
            <script src=
    "https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/js/bootstrap.bundle.min.js" 
                    integrity=
    "sha384-ho+j7jyWK8fNQe+A12Hb8AhRq26LrZ/JpcUGGOn+Y7RsweNrtN/tE3MoK7ZeZDyx" 
                    crossorigin="anonymous"></script>
        </body>
    </html>
    ```