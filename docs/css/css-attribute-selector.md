# CSS |属性选择器

> 原文:[https://www.geeksforgeeks.org/css-attribute-selector/](https://www.geeksforgeeks.org/css-attribute-selector/)

CSS 属性选择器用于选择具有特定属性或属性值的元素。根据某些特定属性对 HTML 元素进行分组是一种很好的样式化方法，属性选择器将选择那些具有相似属性的元素。
属性选择器有几种类型，下面讨论:

*   **[attribute] Selector:** This type of attribute selector is used to select all the elements that have the specified attribute and applies the CSS property to that attribute. For example the selector [class] will select all the elements with the style attribute.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Attributes selector</title>
            <style>
                [class] {
                    text-align:center;
                    Color:green;
                }
                .gfg {
                    font-size:40px;
                    font-weight:bold;
                    margin-bottom:-20px;
                }
            </style>
        </head>
        <body>
            <div class = "gfg">GeeksforGeeks</div>
            <p class = "geeks">A computer science portal for geeks</p>
        </body>
    </html>                    
    ```

    **输出:**
    ![attribute selector](img/50dc47b538eab3b07ed7bffb9d17c462.png)

    这个选择器用于限制某些特定的元素，那么它需要在属性选择器之前指定那个元素。
    **例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Attribute selector</title>
            <style>
                div[style] {
                    text-align:center;
                    color:green;
                    font-size:40px;
                    font-weight:bold;
                    margin-bottom:-20px;
                }
                p {
                    text-align:center;
                    font-size:17px;
                }
            </style>
        </head>
        <body>
            <div style = "color:green">GeeksforGeeks</div>
            <p>A computer science portal for geeks</p>
        </body>
    </html>                    
    ```

    **输出:**
    ![attribute selector](img/5edc5593de9dac82f07a2e4f68d401cb.png)

    可以使用逗号运算符选择多个元素

    ```html
    h2, p[style] {
        background-color: #00b93e;
    }
    ```

*   **[attribute = “value”] Selector:** This selector is used to select all the elements whose attribute has the value exactly same as the specified value.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Attribute selector</title>
            <style>
                [title = "gfg"] {
                    color:green;
                    font-size:40px;
                    font-weight:bold;
                    text-align:center;
                }
                [title = "geeks"] {
                    font-size:17px;
                    text-align:center;
                    margin-top:0px;
                }
            </style>
        </head>
        <body>
            <div title = "gfg">GeeksforGeeks</div>
            <p title = "geeks">A computer science portal for geeks</p>
        </body>
    </html>                    
    ```

    **输出:**
    ![attribute selector](img/5edc5593de9dac82f07a2e4f68d401cb.png)

*   **[attribute~=”value”] Selector:** This selector is used to select all the elements whose attribute value is a list of space-separated values, one of which is exactly equal to the specified value.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Attribute selector</title>
            <style>
                [class~="gfg"] {
                    color:green;
                    font-size:40px;
                    font-weight:bold;
                    text-align:center;
                }
                [class~="geeks"] {
                    font-size:17px;
                    text-align:center;
                    margin-top:0px;
                }
            </style>
        </head>
        <body>
            <div class = "gfg">GeeksforGeeks</div>
            <div Class = "geeks">A computer science portal for geeks
            </div>
            <div class = "geeks ide">GeeksforGeeks is coding platform
            </div>
        </body>
    </html>                    
    ```

    **输出:**
    ![attribute selector](img/925f1209f4b4f4a363e3369b480f40a2.png)

*   **[attribute|=”value”] Selector:** This selector is used to select all the elements whose attribute has a hyphen-separated list of values beginning with the specified value. The value has to be a whole word either alone or followed by a hyphen.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Attribute selector</title>
            <style>
                [class|="gfg"] {
                    color:green;
                    font-size:40px;
                    font-weight:bold;
                    text-align:center;
                }
                [class|="geeks"] {
                    font-size:17px;
                    text-align:center;
                    margin-top:0px;
                }
            </style>
        </head>
        <body>
            <div class = "gfg">GeeksforGeeks</div>
            <div Class = "geeks-ide">A computer science portal for geeks
            </div>
            <div class = "geeks-ide1">GeeksforGeeks is coding platform
            </div>
        </body>
    </html>                                    
    ```

    **输出:**
    ![attribute selector](img/925f1209f4b4f4a363e3369b480f40a2.png)

*   **[attribute^=”value”] Selector:** This selector is used to select all the elements whose attribute value begins with the specified value. The value doesn’t need to be a whole word.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Attribute selector</title>
            <style>
                [class^="gfg"] {
                    color:green;
                    font-size:40px;
                    font-weight:bold;
                    text-align:center;
                }
                [class^="geeks"] {
                    font-size:17px;
                    text-align:center;
                    margin-top:0px;
                }
            </style>
        </head>
        <body>
            <div class = "gfg">GeeksforGeeks</div>
            <div Class = "geeks">A computer science portal for geeks
            </div>
            <div class = "geekside">GeeksforGeeks is coding platform
            </div>
        </body>
    </html>                                    
    ```

    **输出:**
    ![attribute selector](img/925f1209f4b4f4a363e3369b480f40a2.png)

*   **[attribute$=”value”] Selector:** This selector is used to select all the elements whose attribute value ends with the specified value. The value doesn’t need to be a whole word.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Attribute selector</title>
            <style>
                [class$="gfg"] {
                    color:green;
                    font-size:40px;
                    font-weight:bold;
                    text-align:center;
                }
                [class$="geeks"] {
                    font-size:17px;
                    text-align:center;
                    margin-top:0px;
                }
            </style>
        </head>
        <body>
            <div class = "gfg">GeeksforGeeks</div>
            <div Class = "geeksforgeeks">A computer science portal for geeks
            </div>
            <div class = "geeks">GeeksforGeeks is coding platform
            </div>
        </body>
    </html>                                    
    ```

    **输出:**
    ![attribute selector](img/925f1209f4b4f4a363e3369b480f40a2.png)

*   **[attribute*=”value”] Selector:** This selector selects all the elements whose attribute value contains the specified value present anywhere. The value doesn’t need to be a whole word.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Attribute selector</title>
            <style>
                [class*="gfg"] {
                    color:green;
                    font-size:40px;
                    font-weight:bold;
                    text-align:center;
                }
                [class*="for"] {
                    font-size:17px;
                    text-align:center;
                    margin-top:0px;
                }
            </style>
        </head>
        <body>
            <div class = "gfg">GeeksforGeeks</div>
            <div Class = "geeksforgeeks">A computer science portal for geeks
            </div>
            <div class = "geeks for">GeeksforGeeks is coding platform
            </div>
        </body>
    </html>                                    
    ```

    **输出:**
    ![attribute selector](img/925f1209f4b4f4a363e3369b480f40a2.png)