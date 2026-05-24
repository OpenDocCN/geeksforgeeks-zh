# 如何去除 bootstrap 4 中 pre 标签引入的边距？

> 原文:[https://www . geeksforgeeks . org/如何删除页边空白-在引导中引入预标记-4/](https://www.geeksforgeeks.org/how-to-remove-margin-introduced-in-pre-tag-in-bootstrap-4/)

问题是，每当你根据你的利润值应用利润空间时，它就会给你输出。但是在 **[<前置>标签](https://www.geeksforgeeks.org/html-pre-tag/)** 中，如果你通过保留任何空格来应用它，那么它将被视为边距。因为 pre 的作用是相反的，这意味着当您在 pre 标签中写入内容时，输出将是相同的。

**注意:**示例将与引导程序作用相同。

**例 1:** 如果你想写代码并作为普通文本打印出来，基本上使用了前置标签的方法。

*   **程序:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>Pre tag usage</title>
    </head>

    <body>

        <!-- Notice the spces inside of the pre tag -->
        <pre> GeeskforGeeks  </pre>
        <pre> A Computer Science Portal
              For Geeks
        </pre>
    </body>

    </html>
    ```

*   **输出:**

    ```html
     GeeskforGeeks  
     A Computer Science Portal
              For Geeks

    ```

**示例 2:** 有时会发生这样的情况:您已经编写了一些代码，并在 pre 标签内给出了一些空间或边距，然后输出也给出了边距。
在内部预先标记你写代码的方式，它会给出同样的输出。

*   **程序:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>Demo</title>
    </head>

    <body>
        <div class="row">
            <div class="col-md-3">
                <pre>
    <p><b>GeeksforGeeks</b>
    This paragraph is on remove margin
    introduced in pre tag in bootstrap 4</p>
    </pre>
            </div>
        </div>
    </body>

    </html>                    
    ```

*   **输出:**

    ```html
    GeeksforGeeks
    This paragraph is on remove margin
    introduced in pre tag in bootstrap 4
    ```