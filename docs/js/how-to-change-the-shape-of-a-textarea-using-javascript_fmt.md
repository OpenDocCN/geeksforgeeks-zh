# 如何用 JavaScript 改变一个文本区域的形状？

> 原文：[https://www.geeksforgeeks.org/how-to-change-the-shape-of-a-textarea-using-javascript/](https://www.geeksforgeeks.org/how-to-change-the-shape-of-a-textarea-using-javascript/)

一般来说，文本区域将是矩形或正方形的形状，但这里我们将处理文本区域的异常形状，这意味着这个文本区域将不是规则的形状，而是可编辑的。

## 方法 1

在第一种方法中，让我们看看使用 CSS 形状和 `contenteditable` 属性（当其值为 `true` 时）创建的不规则可编辑文本区域。

### 程序 1

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        div {
            top: 124px;
            margin-left: 150px;
            outline: none;
        }

        #parallelogram {
            color: white;
            font-weight: bold;
            width: 250px;
            height: 200px;
            transform: skew(20deg);
            background: #f00;
            overflow: hidden;
        }

        #eq-triangle {
            width: 300px;
            height: 0;
            border-bottom: 104px solid blue;
            /* 104 = 120 * 0.866 */
            border-left: 60px solid transparent;
            border-right: 60px solid transparent;
        }

        .circle {
            display: table-cell;
            padding: 40px;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            font-size: 30px;
            color: #fff;
            line-height: 50px;
            text-align: center;
            background: #40a977;
            word-break: break-all;
            justify-content: center;
            overflow: hidden;
        }
    </style>
</head>

<body>
    <h1>Parallelogram Shaped TextArea</h1>
    <label>
        <h3>Enter Comments:</h3>
    </label>
    <div id="parallelogram" contenteditable="true">
        Enter the something...
    </div>

    <h1>eq-triangle shaped TextArea</h1>
    <label>
        <h3>Enter Comments:</h3>
    </label>
    <div id="eq-triangle" contenteditable="true">
        Enter the something...
    </div>

    <h1>Circle shaped TextArea</h1>
    <label>
        <h3>Enter Comments:</h3>
    </label>
    <div class="circle" contenteditable="true">
        Enter the something...
    </div>
</body>

</html>
```

### 输出

![](img/8028bc6ff4cd576592e874e7937d7115.png)

## 方法 2

使用 JavaScript 更改文本区域的形状。首先使用 `id` 获取元素，然后使用 `style.transform = "skew(40deg)"` 来更改形状。

### 程序 2

让我们用 JavaScript 创建一个不寻常的文本区。

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        textarea {
            color: brown;
            font-weight: bold;
            width: 250px;
            height: 200px;
            background: #ff7;
            overflow: hidden;
        }
    </style>
</head>

<body>
    <center>
        <h1 style="color:green">
            GeeksforGeeks
        </h1>
        <textarea id="myP">
            Unusual shape of a textarea
        </textarea>
        <br>
        <button onclick="myFunction()">
            Try it
        </button>
        <p id="demo"></p>
        <script>
            function myFunction() {
                var x = document.getElementById("myP").style.transform = "skew(40deg)";
                document.getElementById("demo").innerHTML = x;
            }
        </script>
    </center>
</body>

</html>
```

### 输出

**前：**
![](img/dd398ee14f956703e28bc0b80081a89e.png)

**后：**
![](img/d65354eb79103956f9fc3662e26a19e6.png)