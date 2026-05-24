# reactjsgetsnapshotbefore update()方法

> 原文:[https://www . geesforgeks . org/reactjs-getsnapshotbefore update-method/](https://www.geeksforgeeks.org/reactjs-getsnapshotbeforeupdate-method/)

getSnapshotBeforeUpdate()方法是在渲染 DOM 之前调用的。它用于存储 DOM 更新后状态的先前值。

getSnapshotBeforeUpdate()方法返回的任何值都将用作 componentDidUpdate()方法的参数。该函数总是与 componentDidUpdate()方法一起使用，但反之亦然。

**语法:**

```jsx
getSnapshotBeforeUpdate(prevProps, prevState)
```

**参数:**它接受两个参数，它们是 *prevProps* 和 *prevState* ，它们只是重新渲染所讨论的组件之前的道具或状态。

**创建反应应用程序:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即**文件夹名)后，使用以下命令将**移动到该文件夹:

```jsx
cd foldername
```

**示例:**程序演示 getSnapshotBeforeUpdate()方法的使用。在这里，我们将使用状态的先前值和当前值来显示一些文本。

**文件名:App.js:**

## java 描述语言

```jsx
import React from 'react';
class App extends React.Component {

  // Initializing the state
  state = {
    name: 'GFG',
  };

  componentDidMount() {

    // Changing the state after 1 sec
    setTimeout(() => {
      this.setState({ name: 'GeeksForGeeks' });
    }, 1000);
  }

  getSnapshotBeforeUpdate(prevProps, prevState) {

    // Displaying the previous value of the state
    document.getElementById('prev').innerHTML =
      'Previous Name: ' + prevState.name;
  }

  componentDidUpdate() {

    // Displaying the current value of the state
    document.getElementById('new').innerHTML =
      'Current Name: ' + this.state.name;
  }

  render() {
    return (
      <div>
        <div id="prev"></div>
        <div id="new"></div>
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

**输出:**

![](img/abceb8aeeb82d33efc98590938df790a.png)

**参考:**T2【https://reactjs . org/docs/reat-component . html # getsnapshotbefore update