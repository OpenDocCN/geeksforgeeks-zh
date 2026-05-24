# 如何在 React Hooks 中使用 componentWillMount()？

> 原文:[https://www . geeksforgeeks . org/如何使用-component will mount-in-react-hooks/](https://www.geeksforgeeks.org/how-to-use-componentwillmount-in-react-hooks/)

方法允许我们在组件被加载或装载到文档对象模型中时同步执行反应代码。此方法在反应生命周期的安装阶段调用

您不能使用任何现有的反应生命周期方法，如组件装载、组件卸载等。在基于钩子的组件中。为了使用基于类的方法的功能，React hooks 为 componentDidMount、componentDidUpdate 和 componentdemunmount 提供了类似 useEffect Hook 的替代方法，但是对于 componentDidMount()，即使在正式的 React 文档中也没有提供这样的钩子。

根据此[问题](https://github.com/facebook/react/issues/12495)，ComponentWillMount()将在 React 的未来版本中被弃用。建议使用 ComponentDidMount()或 useEffect hook 作为它的替代方法，但是您仍然可以通过将它调用为 UNSAFE _ ComponentWillMount()来使用 ComponentDidMount()。

ComponentWillMount()通常用于在加载组件或从服务器获取数据时显示加载器，但是一旦它被完全弃用，那么我们可以使用暂停作为更好的选择。

**创建反应应用程序:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app functiondemo
```

**步骤 2:** 创建项目文件夹(即 functiondemo)后，使用以下命令移动到该文件夹:

```jsx
cd functiondemo
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例:**在本例中，我们将构建一个应用程序，当组件在 DOM 树中呈现时，该应用程序会记录消息。

**App.js:** 现在在 App.js 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

**使用 componentWillMount()方法:**

## java 描述语言

```jsx
import React from 'react';

class ComponentOne extends React.Component {
  UNSAFE_componentWillMount() {
    console.log('Component is mounted in the DOM');
  }
  render() {
    return <h1>Hello Geeks!</h1>;
  }
}

class App extends React.Component {
  render() {
    return (
      <div>
        <ComponentOne />
      </div>
    );
  }
}

export default App;
```

**使用 useLayoutEffect()方法的替代方案:**

## java 描述语言

```jsx
import React, { useLayoutEffect } from 'react';

const ComponentOne = () => {
  // Defining the useLayoutEffect hook
  useLayoutEffect(() => {
    console.log('Component is mounted in the DOM');
  }, []);

  return <h1>Hello Geeks!</h1>;
};

const App = () => {
  return (
    <div>
      <ComponentOne />
    </div>
  );
};

export default App;
```

**注意:**可以在 App.css 文件中定义自己的样式。

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**

![](img/7f3f248c558ddf21f59ca36694bf8ee4.png)

输出