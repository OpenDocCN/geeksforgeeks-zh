# 如何在 ReactJS 中单个事件处理程序中传递多个道具？

> 原文:[https://www . geeksforgeeks . org/如何通过单个事件处理程序中的多个道具-in-reactjs/](https://www.geeksforgeeks.org/how-to-pass-multiple-props-in-a-single-event-handler-in-reactjs/)

如果我们想在 ReactJS 中的单个事件处理程序中传递/调用多个道具方法，那么有两种方法可以让它工作。

*   **方法 1:** 我们可以为事件单独制作一个方法，调用该方法中的所有道具方法。

    **语法:**

    ```jsx
    const seperateMethod= () => {
     props.method1()
     props.method2()
    }
    ```

*   **方法二**:我们可以创建一个匿名函数，调用匿名方法里面的所有道具方法。

    **语法:**

    ```jsx
    <Component onClick={() => { 
      props.method1(); 
      props.method2() 
    }}>
    </Component>
    ```

**创建反应应用程序:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹:

```jsx
cd foldername
```

**项目结构:**如下图。

![](img/61c6f1343b04abacfcac2db8b7a3d996.png)

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from 'react';
export default class App extends React.Component {

  sayHi = () => {
    alert("Hi from GFG");
  }
  sayHello = () => {
    alert("Hello from GFG");
  }

  render() {
    return (
      <div style={{ marginLeft: 50 }}>
        <Child1 m1={this.sayHi} 
                m2={this.sayHello} >
        </Child1>
        <br></br>
        <Child2 m1={this.sayHi} 
                m2={this.sayHello}>
        </Child2>
      </div>
    )
  }
}

// Method 1
class Child1 extends React.Component {

  seperatemethod = () => {
    this.props.m1();
    this.props.m2();
  }

  render() {
    return (
      <div>
        <button onClick={this.seperatemethod}>
          Hello Hi from GFG
        </button>
      </div>
    )
  }
}

// Method 2
class Child2 extends React.Component {

  render() {
    return (
      <div>
        <button onClick={() => {
          this.props.m1();
          this.props.m2();
        }}
        >Hello hi from GFG</button>
      </div>
    )
  }
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/73ce5199514613554d52b53499fa1b32.png)

**解释:**从上面的代码中我们可以看到，Child1 组件使用方法 1，通过创建一个单独的方法来调用多个道具，child2 组件通过创建一个匿名方法来调用多个道具。