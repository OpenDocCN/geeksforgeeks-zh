# react . js 中的文件上传

> 原文:[https://www.geeksforgeeks.org/file-uploading-in-react-js/](https://www.geeksforgeeks.org/file-uploading-in-react-js/)

对于任何设想构建应用程序的开发人员来说，上传图像是他们必须考虑的一个主要部分。这是创建完整应用程序的基本要求。文件上传意味着来自客户端机器的用户想要将文件上传到服务器。比如用户可以在脸书、Instagram 上传图片、视频等。与任何编程问题一样，有许多方法可以实现这一结果。本文解释了一种简单的方法来实现用 React 上传单个文件的方法。
上传图片的过程大致可以分为两个步骤:

*   **选择一个文件(用户输入):**要使用户能够挑选文件，第一步是将标签添加到我们的 App 组件中。该标记应该将类型属性设置为“文件”。现在，我们需要一个事件处理程序来监听对文件所做的任何更改。每当用户选择一个新文件时都会触发此事件处理程序，并将更新状态。
*   **向服务器发送请求:**存储完选中的文件(处于状态)后，我们现在需要将其发送到服务器。为此，我们可以使用 fetch 或 Axios。(在这段代码中，我们使用 Axios 作为浏览器和节点的基于承诺的 HTTP 客户端)。该文件被发送到包装在 FormData 对象中的服务。
    T3】安装 Axios:
    *   运行以下命令。

```jsx
npm install axios --save
```

打开您的 react 项目目录，从 src 文件夹编辑 **App.js** 文件:

**src App.js:**

## java 描述语言

```jsx
import axios from 'axios';

import React,{Component} from 'react';

class App extends Component {

    state = {

      // Initially, no file is selected
      selectedFile: null
    };

    // On file select (from the pop up)
    onFileChange = event => {

      // Update the state
      this.setState({ selectedFile: event.target.files[0] });

    };

    // On file upload (click the upload button)
    onFileUpload = () => {

      // Create an object of formData
      const formData = new FormData();

      // Update the formData object
      formData.append(
        "myFile",
        this.state.selectedFile,
        this.state.selectedFile.name
      );

      // Details of the uploaded file
      console.log(this.state.selectedFile);

      // Request made to the backend api
      // Send formData object
      axios.post("api/uploadfile", formData);
    };

    // File content to be displayed after
    // file upload is complete
    fileData = () => {

      if (this.state.selectedFile) {

        return (
          <div>
            <h2>File Details:</h2>

<p>File Name: {this.state.selectedFile.name}</p>

<p>File Type: {this.state.selectedFile.type}</p>

<p>
              Last Modified:{" "}
              {this.state.selectedFile.lastModifiedDate.toDateString()}
            </p>

          </div>
        );
      } else {
        return (
          <div>
            <br />
            <h4>Choose before Pressing the Upload button</h4>
          </div>
        );
      }
    };

    render() {

      return (
        <div>
            <h1>
              GeeksforGeeks
            </h1>
            <h3>
              File Upload using React!
            </h3>
            <div>
                <input type="file" onChange={this.onFileChange} />
                <button onClick={this.onFileUpload}>
                  Upload!
                </button>
            </div>
          {this.fileData()}
        </div>
      );
    }
  }

  export default App;
```