# 反应还原简介

> 原文：[https://www.geeksforgeeks.org/introduction-to-react-redux/](https://www.geeksforgeeks.org/introduction-to-react-redux/)

熟悉`react`的人会知道`react`是一个基于组件的前端库工具，它连接了网页的各个部分。在`react`中，我们在允许使用非静态变量的组件中使用`props`（`properties`的缩写）。在`props`的帮助下，我们可以将这些变量从父组件传递到各种其他组件（子组件）中。

示例：将`props`从父组件传递到子组件：

```jsx
import React, { Component } from 'react';
class App extends Component {
  render() {
    const wishes = 'Welcome to My World';
    return (
      <div>
        <Greeting wishes={wishes} />
      </div>
    );
  }
}
class Greeting extends Component {
  render() {
    return <h1>Welcome to {this.props.wishes} world!!</h1>;
  }
}
export default App;
```

`react`中状态的存在允许定义组件自身的变量。在我们的应用程序中有一些组件，我们可以将这些状态作为`props`传递给子组件。但是随着应用程序中的组件数量根据其大目标而增加，我们需要将这些状态传递给组件树中彼此远离的其他组件。此时，将状态作为`props`传递的通常方式变得复杂，因为并非每个组件都是需要状态的组件的父组件。

示例：初始化组件中的状态，并将其作为`props`传递给其子组件：

```jsx
class Parent extends Component{
 constructor(props){
  super(props);
  this.state={
   child1=0;
   child2=1;
  };
 }
 render()
 {
  return (
   <Child1 value={this.state.child1} />
   <Child2 value={this.state.child2} />
  );
 }
}
```

这就需要在我们的`react`应用中使用`react-redux`。`React-redux`作为一个状态管理工具，可以更容易地将这些状态从一个组件传递到另一个组件，而不考虑它们在组件树中的位置，从而避免了应用程序的复杂性。

## 工作程序

当`react`应用程序从其他组件中获取各种需要状态的组件时，很难意识到状态应该驻留在这些组件中的什么位置，以便于维护。`React-redux`提供了一个`store`，使组件内部的状态更容易维护。与`store`一起，`react-redux`引入了`actions`和`reducers`，它们与`store`同时工作，使状态更加可预测。`react-redux`中功能的工作原理解释如下：

*   **Store**：包含需要传递给其他组件的组件的状态。`store`使这种传递变得容易得多，因为我们不再需要在父组件内部维护一个状态来将其传递给子组件。
*   **Actions**：`react-redux`的`actions`部分基本上包含了要对`store`中存在的状态执行的不同动作。包含的操作必须包含操作类型，还可以包含有效负载（操作中的数据字段）。
    示例：`react`应用中的增量和减量动作：

```jsx
export const increment = (num) => {
    return{
        type: 'INCREMENT',
        payload: num
    };
};

export const decrement = () => {
    return{
        type: 'DECREMENT',
    };
};
```

*   **Reducer**：`react-redux`中的`reducer`是包含需要对状态执行的操作的纯函数。这些函数接受正在使用的状态的初始状态和动作类型。它更新状态并用新的状态进行响应。该更新的状态被发送回`react`的视图组件，以进行必要的更改。`reducer`必须包含动作类型。
    示例：根据动作类型更新状态的`reducer`。
    程序 1：

```jsx
const counterReducer = (state=0, action) => {
 switch(action.type)
 {
  case 'INCREMENT':
   return state + action.payload;
  case 'DECREMENT':
   return state - 1;
  default:
   return state;
 }
};
```

程序 2：创建接受`reducer`的`store`的片段。

```jsx
import {createStore} from 'react-redux';

const store = createStore(
 counterReducer,
 window.__REDUX_DEVTOOLS_EXTENSION__ &&
    window.__REDUX_DEVTOOLS_EXTENSION__()
);
```

## React-Redux 所需的

如上所示，很明显，`React-Redux`的使用在我们的应用程序中引入了大量的样板代码，只是为了将状态从一个组件传递到另一个组件。这可能会导致许多新的`react-redux`学习者从相同的内容中撤回他们的兴趣。尽管如此，许多开发人员在他们的应用程序中更喜欢`react-redux`，原因如下：

*   **降低代码复杂性**：如前所述，当一个应用程序包含大量通过其状态相互交互的组件时，将一个组件的状态作为`props`传递给位于组件树远处的另一个组件变得很难管理。`React-redux`引入了`store`来保存应用程序组件的状态，从而使代码变得更简单，因为它消除了状态应该驻留在哪里的混乱。
*   **更容易维护**：在`store`的帮助下，状态现在位于应用程序中的一个位置，这使得每当各种组件中发生状态更新时，都更容易维护。
*   **减少时间**：`React-redux`刷新页面的各个部分，而不是重新加载整个页面，因此节省了我们的时间。
*   **轻松调试**：`React-redux`引入了`reducer`，这些`reducer`是在状态下运行的纯函数，这使得逻辑更简单，有助于实现轻松调试。

## 安装

要在您的`react`应用程序中安装`react-redux`，请在终端中运行以下命令：

```bash
npm install react-redux
```

## 参考

[https://react-redux.js.org/](https://react-redux.js.org/)