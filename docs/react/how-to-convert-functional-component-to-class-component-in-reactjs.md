# 如何在 ReactJS 中将功能组件转换为类组件？

> 原文:[https://www . geesforgeks . org/如何将功能组件转换为类组件 in-reactjs/](https://www.geeksforgeeks.org/how-to-convert-functional-component-to-class-component-in-reactjs/)

如果我们想把一个函数组件转换成一个类组件，那么我们需要做以下主要的改变。

1.  将函数更改为类
2.  添加渲染方法
3.  将所有函数转换为方法
4.  添加构造函数
5.  用生命周期方法替换钩子

**创建反应应用程序:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序:

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹:

    ```jsx
    cd foldername
    ```

**项目结构:**如下图。

![](img/7741c5c80ef4f444b97fd777e206a1c3.png)

**示例:功能组件**

在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React, { useState } from 'react';

function App(props) {

  const [counter, setCounter] = useState(0);
  const myFunction = (e) => {
    alert("The value of counter is " + counter)
    setCounter(counter + 1);
  }

  return (
    <div>

<p>Hello, {props.name}</p>

      <button onClick={myFunction}>Click me!</button>
    </div>
  );
}

export default App;
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/38cd350f1e502d9220d0d233a3309e38.png)

**示例:类组件**

使用上述步骤将函数组件转换为类组件，我们在 **App.js** 文件中编写了以下代码。

## App.js

```jsx
import React, { useState } from 'react';

class App extends React.Component {

  constructor(props) {
    super(props)
    this.state = {
      counter: 0
    }
    this.myFunction = this.myFunction.bind(this);
  }

  myFunction(e) {
    alert("The value of counter is " + this.state.counter)
    this.setState({ counter: this.state.counter + 1 })
  }

  render() {
    return (
      <div >
        <p>Hello From GFG</p>

        <button onClick={this.myFunction}>
         Click me!
        </button>
      </div>
    );
  }
}

export default App;
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/38cd350f1e502d9220d0d233a3309e38.png)