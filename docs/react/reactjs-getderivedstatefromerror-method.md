# reactjsgetderivedstateformerror()方法

> 原文:[https://www . geeksforgeeks . org/reactjs-getderivedstateformerror-method/](https://www.geeksforgeeks.org/reactjs-getderivedstatefromerror-method/)

如果在任何生命周期方法或任何子组件的呈现阶段出现错误，将调用 getDerivedStateFromError()方法。此方法用于实现反应应用程序的错误边界。它在渲染阶段被调用，所以在这个方法中不允许有副作用。对于副作用，请改用 componentDidCatch()。

**语法:**

```jsx
static getDerivedStateFromError(error)
```

**参数:**它接受作为参数抛出的错误。

**创建反应应用程序:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名称)后，使用以下命令移动到该文件夹:

```jsx
cd foldername
```

**示例**:演示 getDerivedStateFromError()方法使用的程序。

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

**文件名:App.js**

## java 描述语言

```jsx
import React, { Component } from 'react';

export default class App extends Component {

  // Initializing the state
  state = {
    error: false
  };

  static getDerivedStateFromError(error) {
    // Changing the state to true if some error occurs
    return {
      error: true,
    };
  }

  render() {
    return (
      <React.StrictMode>
        <div>
          {this.state.error ? <div>Some error</div> : <GFGComponent />}
        </div>
      </React.StrictMode>
    );
  }
}

class GFGComponent extends Component {

  // GFGComponent throws error as state of GFGCompnonent is not defined
  render() {
    return <h1>{this.state.heading}</h1>;
  }
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**

![](img/cadf225322e9712950f999af0a6f662e.png)

**参考:**[https://reactjs . org/docs/react-component . html # static-getderivedstateformerror](https://reactjs.org/docs/react-component.html#static-getderivedstatefromerror)