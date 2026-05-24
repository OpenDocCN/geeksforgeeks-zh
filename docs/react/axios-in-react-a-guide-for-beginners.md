# Axios in React:初学者指南

> 原文:[https://www . geesforgeks . org/axios-in-react-a-guide-for-初学者/](https://www.geeksforgeeks.org/axios-in-react-a-guide-for-beginners/)

在科技行业，很多前端框架都很流行，React 就是其中之一。用任何后端语言使用这个框架都不容易。为了与数据库进行通信，开发人员必须遵循特定的规则，并且他们必须编写特定的代码行。

在 React 中，与后端服务器的通信是通过 HTTP 协议完成的。如果您是开发人员，那么您可能已经熟悉了 XML Http Request 接口和 Fetch API。它允许您获取数据和发出 HTTP 请求。

这是 React 中与数据库通信的常用方法。在 React 中，还有另一种与后端服务器通信的方法，这需要安装一个流行的库 Axios。

在本文中，我们将讨论这个库、它的关键特性，以及 Axios 如何在不同情况下与数据库通信。

**Axios 简介:** Axios 是一个流行的库，主要用于向 REST 端点发送异步 HTTP 请求。这个库对于执行 CRUD 操作非常有用。

1.  This popular library is used to communicate with the backend. Axios supports Promise API and is native to JS ES6.
2.  With Axios, we make API requests in the application. Once the request is made, we get the data in Return and then use it in our project.
3.  This library is very popular among developers. You can check it on GitHub, and you will find that there are 78k stars on it.

在安装 Axios 之前，您的 React 项目应用程序应该准备好安装该库。按照下面给出的步骤创建一个 React 应用程序……

*   **第一步:**下面是在你的项目中创建 React app 的命令……

    ```jsx
    npx create-react-app new_files
    ```

*   **第二步:**进入第一步创建的目录。

    ```jsx
    cd new_files
    ```

*   **步骤 3:** 使用下面给出的命令安装 Axios 库……

    ```jsx
    npm install axios
    ```

*   **步骤 4:** 完成后，您可以使用下面给出的命令启动服务器..

    ```jsx
    npm start
    ```

安装 Axios 后，您可以将该库导入到您的文件中，并使用它发出 HTTP 请求。下面是一个文件的代码片段，其中库在顶部导入…

## java 描述语言

```jsx
import React from "react";
import axios from "axios";

class App extends React.Component {
  state = {
    newfiles: null,
  };

  handleFile(e) {

    // Getting the files from the input
    let newfiles = e.target.newfiles;
    this.setState({ newfiles });
  }

  handleUpload(e) {
    let newfiles = this.state.newfiles;

    let formData = new FormData();

    // Adding files to the formdata
    formData.append("image", newfiles);
    formData.append("name", "Name");

    axios({

      // Endpoint to send files
      url: "http://localhost:8080/files",
      method: "POST",
      headers: {

        // Add any auth token here
        authorization: "your token comes here",
      },

      // Attaching the form data
      data: formData,
    })

      // Handle the response from backend here
      .then((res) => { })

      // Catch errors if any
      .catch((err) => { });
  }

  render() {
    return (
      <div>
        <h1>Select your files</h1>
        <input
          type="file"

          // To select multiple files
          multiple="multiple"
          onChange={(e) => this.handleFile(e)}
        />
        <button onClick={(e) => this.handleUpload(e)}>
          Send Files
        </button>
      </div>
    );
  }
}

export default App;
```

上面的例子只是一个小代码描述，展示了如何在您的项目中使用 Axios。我们将在下一节讨论多种方法，如 Axios 中的 GET、POST、PUT。

**Axios 在 React 中的需求:**正如我们已经讨论过的，Axios 允许您与 React 项目中的 API 进行通信。同样的任务也可以通过使用 AJAX 来执行，但是 Axios 为您提供了更多的功能和特性，这有助于您快速构建应用程序。

Axios 是一个基于承诺的库，所以你需要实现一些基于承诺的异步 HTTP 请求。jQuery 和 AJAX 也执行相同的工作，但是在 React 项目中，React 处理它自己的虚拟 DOM 中的每一个和所有内容，因此根本不需要使用 jQuery。

下面是使用 Axios……

## Javascript

```jsx
const getCustomersData = () => {
  axios
  .get("https://jsonplaceholder.typicode.com/customers")
  .then(data => console.log(data.data))
  .catch(error => console.log(error));
  };
 getCustomersData();
```

获取客户数据的示例

现在让我们进入下一个要点，了解如何执行不同的操作，例如使用 Axios (GET-POST-DELETE)提取数据或消费数据。

**使用 Axios 获取请求:**创建一个组件 MyBlog，并将其挂钩到组件 DidMount 生命周期中。在顶部导入Axios，并根据获取请求获取数据。

## Javascript

```jsx
import React from 'react';
 import axios from 'axios';
 export default class MyList extends React.Component {
  state = {
    blogs: []
  }
  componentDidMount() {
    axios.get(`https://jsonplaceholder.typicode.com/posts`)
    .then(response => {
      const posts = response.data;
      this.setState ({posts});
    })
  }
 render() {
  return (
   < ul >
     {this.state.posts.map (post =>  {post.title} )}
   < /ul >
  )}
 }
```

这里我们使用 axios.get (URL)来获得一个返回响应对象的承诺。返回的响应被分配给帖子的对象。我们还可以检索其他信息，如状态码等。

**使用 Axios 的开机自检请求:**为开机自检请求创建一个新组件添加开机自检。此请求将在帖子列表中添加帖子。

## Javascript

```jsx
import React from 'react';
import axios from 'axios';
export default class AddPost extends React.Component {
   state = {
     postTitle: '',
   }
   handleChange = event => {
     this.setState({ postTitle: event.target.value });
   }
   handleSubmit = event => {
     event.preventDefault();
       const post = {
         postName: this.state.postName
       };
     axios.post(
`https://jsonplaceholder.typicode.com/posts`, { post })
       .then(res => {
         console.log(res);
         console.log(res.data);
     })
     [Text Wrapping Break] 
     }
    render() {
         return (
         <div>
           <form onSubmit="{this.handleSubmit}">
             <label>
               Post Name:
               <input type="text" name="name" 
                     onChange="{this.handleChange}" />
             </label>
             <button type="submit">Add</button>
          </form>
        </div>
 )}}
```

在上面的代码中，我们发出了一个 HTTP Post 请求，并向数据库中添加了一个新的 Post。onChange 事件触发 handleChange()方法，并在 API 请求成功返回数据时更新请求。

**使用 axios 删除请求:**将删除请求发送到服务器 Axios。使用 Delete。在创建这个请求 URL 和可选配置时，您需要指定两个参数。

```jsx
axios.delete(url, { 
  data: { foo: "bar" }, 
  headers: { "Authorization": "******" } 
}); 
```

发送删除请求时，您必须设置请求正文和标题。为此，请使用 config.data。在上面的 POST 请求中，修改下面给出的代码……

## Javascript

```jsx
handleSubmit = event => {
  event.preventDefault();
  axios.delete(
`https://jsonplaceholder.typicode.com/posts/${this.state.postName}`)
  .then(res => {
  console.log(res);
  console.log(res.data);
  })
}
```

**Axios 中的响应对象:**当您向服务器发送请求时，您将从服务器收到一个响应对象，其属性如下所示……

*   **Data:** You will receive data in the form of payload from server. These data are returned as JSON, and parses back into a JavaScript object.
*   **Status:** You get the HTTP code returned by the server.
*   **Status text:** HTTP status message returned by the server.
*   **Header:** All headers are sent back by the server.
*   **Configuration:** Configuration originally requested.
*   **请求:** 实际 XMLHttpRequest 对象

**错误对象:**如果请求有问题，你会得到一个错误对象。承诺将被拒绝，错误对象为下面给出的属性。

*   **Message:** Text of error message.
*   **Response:** The response object (if received).
*   **Request:** The actual XMLHttpRequest object (when running in the browser).
*   **Configuration:** Configuration originally requested.

**Axios 库的特性**

*   Automatic transformation of JSON data.
*   It converts request and response data.
*   Used to make HTTP requests from Node.js
*   It sends out xmlhttp requests from the browser.
*   Provide client support to prevent XSRF.
*   Support the promise API.
*   The ability to cancel the request.

**Axios 中的速记方法:**下面是 Axios 的一些速记方法……

*   Axios。请求(配置)
*   Axios . head(URL，[配置])
*   Axios . get(URL，url 配置)
*   Axios . post(URL、【日期】、【配置】
*   Axios。放(网址【，数据【，配置】)
*   Axios . delete(URL)

### 结论

这篇文章解释了关于 Axios 库的一切。我们已经讨论了一些有用的操作，例如在 Axios 中提取数据、发布数据、更新数据或删除数据。一旦开始使用 React，就必须使用这个库与数据库服务器进行通信。因此，对它进行实践并了解它在 Axios 中是如何工作的非常重要。