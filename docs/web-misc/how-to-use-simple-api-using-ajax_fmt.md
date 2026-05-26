# 如何使用 AJAX 调用简单的 API？

> 原文：[https://www.geeksforgeeks.org/how-to-use-simple-api-using-ajax/](https://www.geeksforgeeks.org/how-to-use-simple-api-using-ajax/)

AJAX（异步 JavaScript 和 XML）是一组用于调用服务器获取数据的工具。在本文中，我们将看到如何使用 AJAX 实现一个简单的 API 调用。

## 先决条件
对 AJAX 及其功能有基础知识。你可以从这里[学习所有基础知识](https://www.geeksforgeeks.org/ajax-introduction/)。

## 基本架构
我们将从一个免费的 API 获取员工对象中的员工姓名，并将其显示在一个列表中。网上有很多免费的 API，你可以使用任何一个。

## HTML 代码
我们有一个用于获取数据的按钮和一个空的无序列表，我们将使用 JavaScript 动态地向其中添加列表项。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Required meta tags -->
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,
        initial-scale=1, shrink-to-fit=no" />

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
        integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
        crossorigin="anonymous" />

    <title>
        How to use simple API using AJAX ?
    </title>
</head>

<body>
    <button type="button" id="fetchBtn"
        class="btn btn-primary">
        Fetch Data
    </button>

    <div class="container">
        <h1>Employee List</h1>
        <ul id="list"></ul>
    </div>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="Ajax.js"></script>
    <script src=
"https://code.jquery.com/jquery-3.2.1.slim.min.js"
        integrity=
"sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
        crossorigin="anonymous">
    </script>

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
        integrity=
"sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q"
        crossorigin="anonymous">
    </script>

    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
        integrity=
"sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
        crossorigin="anonymous">
    </script>
</body>

</html>
```

## AJAX 代码

### 第一步
获取按钮元素，使用 `getElementById` 方法。

### 第二步
给按钮添加一个 `addEventListener`，并为其提供回调函数。

### 第三步
使用 `new` 关键字实例化一个 `XMLHttpRequest` 对象。

### 第四步
使用 `open` 方法打开一个请求。它需要三个参数：第一个是类型（`GET` 或 `POST`），第二个是 API 的 URL，最后一个是布尔值（`true` 表示异步调用，`false` 表示同步调用）。

### 第五步
现在我们使用 `onload` 函数来显示数据。`onload` 函数在 API 调用完成后执行。我们将检查成功的状态码，用 `200` 来判断，因为 `200` 是 HTTP 请求的成功代码。

### 第六步
现在，我们将使用 `JSON.parse` 将其转换成一个 JSON 对象，这样我们就可以轻松地从中获取数据。

### 第七步
在这一步中，我们将使用 `for...in` 循环迭代对象中的所有项目，并使用 `innerHTML` 属性将其添加到列表中。

### 第八步
最后一步是使用 `send()` 函数发送请求。

下面是上述步骤的实现。为了使代码易于理解，我们还在每一行提供了注释。

```html
<script>
    let fetchBtn = document.getElementById("fetchBtn");

    fetchBtn.addEventListener("click", buttonclickhandler);

    function buttonclickhandler() {
        // Instantiate a new XHR Object
        const xhr = new XMLHttpRequest();

        // Open an object (GET/POST, PATH, ASYN-TRUE/FALSE)
        xhr.open("GET", "http://dummy.restapiexample.com/api/v1/employees", true);

        // When response is ready
        xhr.onload = function () {
            if (this.status === 200) {
                // Changing string data into JSON Object
                obj = JSON.parse(this.responseText);

                // Getting the ul element
                let list = document.getElementById("list");
                str = ""
                for (key in obj.data) {
                    str += `<li>${obj.data[key].employee_name}</li>`;
                }
                list.innerHTML = str;
            }
            else {
                console.log("File not found");
            }
        }

        // At last send the request
        xhr.send();
    }
</script>
```

## 完整代码
这是以上两个代码段的组合。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Required meta tags -->
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,
            initial-scale=1, shrink-to-fit=no" />

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
        integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
        crossorigin="anonymous" />

    <title>
        How to use simple API using AJAX ?
    </title>
</head>

<body>
    <button type="button" id="fetchBtn"
            class="btn btn-primary">
        Fetch Data
    </button>

    <div class="container">
        <h1>Employee List</h1>
        <ul id="list"></ul>
    </div>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script>
        let fetchBtn = document.getElementById("fetchBtn");

        fetchBtn.addEventListener("click", buttonclickhandler);

        function buttonclickhandler() {
            // Instantiate a new XHR Object
            const xhr = new XMLHttpRequest();

            // Open an object (GET/POST, PATH, ASYN-TRUE/FALSE)
            xhr.open("GET", "http://dummy.restapiexample.com/api/v1/employees", true);

            // When response is ready
            xhr.onload = function () {
                if (this.status === 200) {
                    // Changing string data into JSON Object
                    obj = JSON.parse(this.responseText);

                    // Getting the ul element
                    let list = document.getElementById("list");
                    str = ""
                    for (key in obj.data) {
                        str += `<li>${obj.data[key].employee_name}</li>`;
                    }
                    list.innerHTML = str;
                }
                else {
                    console.log("File not found");
                }
            }
            xhr.send();
        }
    </script>

    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"
        integrity=
"sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
        crossorigin="anonymous">
    </script>

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
        integrity=
"sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q"
        crossorigin="anonymous">
    </script>

    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
        integrity=
"sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
        crossorigin="anonymous">
    </script>
</body>

</html>
```

## 输出
![](img/bca561fb44875a2635be42cce058b5cc.png)