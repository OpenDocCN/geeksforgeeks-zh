# 如何创建一个引导微调器并在屏幕上显示，直到从应用编程接口加载数据？

> 原文:[https://www . geeksforgeeks . org/如何创建引导旋转器并在屏幕上显示，直到 api 加载数据/](https://www.geeksforgeeks.org/how-to-create-a-bootstrap-spinner-and-display-on-screen-till-the-data-from-the-api-loads/)

任务是在页面上显示一个微调器，直到来自 API 的数据响应到来。我们用 bootstrap spinner 来展示这个例子。

**先决条件:**

*   你将需要一些关于 [JavaScript 获取 API](https://www.geeksforgeeks.org/how-to-use-the-javascript-fetch-api-to-get-data/) 的知识。
*   您将需要一个模拟应用编程接口来获取数据。

**进场:**

*   为任务创建必要的 HTML、CSS 和 JavaScript 文件。
*   在 HTML 文件中，链接**头部的引导。**

    > <link rel="”stylesheet”" href="”https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css”" integrity="”sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh”" crossorigin="”anonymous”">

*   现在拿“https://getbootstrap.com/docs/4.4/components/spinners/”中的任意一个旋转器来说，我举的例子是:

    ```html
    <div class="spinner-border text-primary" 
        id="spinner"role="status">
        <span class="sr-only">Loading...</span>
    </div>

    ```

*   现在，一旦来自 API 的数据被加载，spinner 将不得不停止。
*   所以，通过 **Fetch() API 方法从 API 获取数据。**
*   将数据存储在**响应**变量中。
*   有一个 if 语句检查来自 API 的**响应是否到来**。
*   如果响应来了，那么有一个**函数 hideSpinner()** 被调用。
*   在**隐藏微调器()功能**中，通过使用 **DOM 操作**，我们将**微调器元素的显示设置为无**。

**HTML 文件:**

```html
<!DOCTYPE html>
<html>

<head>
    <script src="script.js"></script>
    <title>Spinner</title>
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
        integrity=
"sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
        crossorigin="anonymous">
</head>

<body>
    <div class="spinner-border text-primary" 
        id="spinner" role="status">
        <span class="sr-only">Loading...</span>
    </div>
    <div id="data"></div>
</body>

</html>
```

**JavaScript 文件:**

```html
// API url 
const api_url =
"https://mygfgapi.free.beeceptor.com/my/api/path";

// Defining async function 
async function getapi(url) {

    // Storing response 
    const response = await fetch(url);

    // Storing data in form of JSON 
    var apidata = await response.json();
    console.log(apidata);
    if (response) {
        hideSpinner();
    }
    document.getElementById("data").innerHTML
        = `<h1>${apidata.data}</h1>`;
}

// Calling that async function 
getapi(api_url);

// Function to hide the Spinner
function hideSpinner() {
    document.getElementById('spinner')
            .style.display = 'none';
} 
```

**输出:**

您可以在输出窗口中看到，微调器一直加载到来自应用编程接口的数据到来。

![](img/48ff45ae7fd4908aa366bec7ab9daeba.png)

**API 链接:***【https://mygfgapi . free . beeeceptor . com/my/API/path】*