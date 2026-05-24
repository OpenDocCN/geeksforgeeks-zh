# 通过定制 HTTP 库

使用 AJAX 发布请求

> 原文:[https://www . geesforgeks . org/post-request-use-Ajax-by-making-custom-http-library/](https://www.geeksforgeeks.org/post-request-using-ajax-by-making-custom-http-library/)

任务是展示如何通过定制 HTTP 库将 **XMLHttpRequest** 用于**将**数据发布到应用编程接口。我们将以一个包含对象数组的假应用编程接口为例，通过定制 HTTP 库，我们将通过 **XMLHttpRequest** 方法向**发布**数据。

**使用的原料药:**[https://jsonplaceholder.typicode.com/posts](https://jsonplaceholder.typicode.com/posts)

**什么是 Ajax？**
**Ajax** 或异步 JavaScript 和 **XML** 用于与服务器通信，无需刷新网页，从而增加用户体验和更好的性能。要了解更多关于 **Ajax** 的信息，请点击[https://www.geeksforgeeks.org/ajax-introduction/.](https://www.geeksforgeeks.org/ajax-introduction/.)

**先决条件:**只需要 HTML、CSS、JavaScript 的基础知识就可以了。

**注意:**首先制作一个 HTML 文件，根据需求添加 HTML 标记。在 body 标签的底部，以相同的顺序附加两个脚本文件，如 library.js 和 app.js。

**制作 library.js 文件所需的步骤:**

1.  在 library.js 文件中，做一个函数 **easyHTTP** 初始化一个新的 **XMLHttpRequest()** 方法。
2.  将 **easyHTTP.prototype.post** 设置为包含三个参数的函数**【URL】【数据】****回调**。
3.  现在使用**这个. http.open** 函数打开一个对象。它需要三个参数，第一个是请求类型(GET 或 POST 或 PUT 或 DELETE)，第二个是 API 的 URL，最后一个是布尔值(true 表示异步调用，false 表示同步调用)。
4.  现在我们使用 **onload** 功能显示数据。但在此之前，我们首先需要用**this . http . setrequestheader**方法设置内容类型，并且还需要将**这个**关键字**T7】分配给**自己**，使**这个**关键字的范围进入 **onload** 功能。 **onload** 函数在完成 API 调用后执行。该函数将运行一个**回调**函数，该函数有两个参数作为错误和响应文本。**
5.  最后一步是使用 **send()** 功能发送请求。需要注意的是， **send()** 函数使用 **JSON.stringify(data)** 将对象数据转换为字符串后需要发送数据。

**制作 app.js 文件所需的步骤:**

1.  首先用**新的**关键字实例化 **easyHTTP** 。
2.  创建一个自定义数据(**对象**)进行发布。
3.  在**帖子**原型函数中传递 URL、数据和一个回调函数。
4.  回调函数包含两个参数:如果出现任何错误，将打印的错误和获取实际响应的响应。

**文件名:index.html**

```htmlhtml
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
    <title>POST request</title>
</head>
<body>
    <h1>
        POST request using xmlhttpRequest/Ajax 
        by making custom HTTP library.
    </h1>

    <!-- including library.js and app.js files -->
    <script src="library.js"></script>
    <script src="app.js"></script>
</body>

</html>
```

**文件名:app.js**

```htmlhtml
// Instantiating easyHTTP
const http = new easyHTTP;

// Create Data
const data = {
  title: 'Custom HTTP Post',
  body: 'This is a custom post data'
};

// Post prototype method(url, data,
// response text)
http.post(
'https://jsonplaceholder.typicode.com/posts',
   data, 
   function(err, post) {
      if(err) {
        console.log(err);
      } else {
        // Parsing string data to object
        // let data = JSON.parse(posts); 
        console.log(post);
    }
});
```

**文件名:library.js**

```htmlhtml
  function easyHTTP() {

    // Initializing new XMLHttpRequest method. 
    this.http = new XMLHttpRequest();
  }

  // Make an HTTP POST Request
  easyHTTP.prototype.post = function(url, data, callback) {

  // Open an object (POST, PATH, ASYN-TRUE/FALSE) 
  this.http.open('POST', url, true);

  // Set content-type
  this.http.setRequestHeader('Content-type', 'application/json');

  // Assigning this to self to have  
  // scope of this into the function
  let self = this;

  // When response is ready 
  this.http.onload = function() {

    // Callback function (Error, response text)
    callback(null, self.http.responseText);
  }

  // Since the data is an object so
  // we need to stringify it
  this.http.send(JSON.stringify(data));
}
```

**输出:**
在任意浏览器中打开您的**index.html**文件，通过**右键- >检查元素- >控制台**打开其控制台。因此你会看到下面的结果。

**注意:**它包含一个额外的键值对作为‘id’101。不要担心这个，因为这是默认创建的。
T3】