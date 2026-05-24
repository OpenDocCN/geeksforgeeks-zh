# CSS |对齐自属性

> 原文:[https://www.geeksforgeeks.org/css-align-self-property/](https://www.geeksforgeeks.org/css-align-self-property/)

CSS 中的 **align-self 属性**用于以多种不同的方式对齐柔性容器中的选定项目，如弯曲结束、居中、弯曲开始等。

**语法:**

```html
align-self: auto|stretch|center|flex-start|flex-end|baseline|
initial;
```

**属性值:**
**自动:**此属性用于继承其父容器 align-items 属性，如果没有父容器，则用于拉伸。这是一个默认值。

*   **语法:**

    ```html
    align-self: auto;
    ```

*   **Example:**

    ## Hypertext Markup Language

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS | align-self Property
    </title>
    <style>
        #geeks {
            width: 250px;
            height: 200px;
            border: 4px solid black;
            display: -webkit-flex;
            -webkit-align-items: flex-start;
            display: flex;
            align-items: flex-start;
        }

        #geeks div {
            -webkit-flex: 2;
            flex: 1;
        }

        #sudo {
            -webkit-align-self: auto;
            align-self: auto;
        }
    </style>
</head>

<body>
    <center>
        <h2 style="color:green;">
          GeeksForGeeks
        </h2>
        <h3 style="color:green;">
          align-self:auto;
        </h3>
        <div id="geeks">
            <div style="background-color:green;color:white;">
              Geeks
            </div>
            <div style="background-color:lightblue;"
                 id="sudo">
              For
            </div>
            <div style="background-color:coral;">
              Geeks
            </div>
            <div style="background-color:lightblue;">
              Sudo
            </div>
            <div style="background-color:tomato;">
              Placement
            </div>
        </div>
    </center>
</body>

</html>         
```