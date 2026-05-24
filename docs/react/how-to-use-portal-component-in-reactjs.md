# 如何在 ReactJS 中使用门户组件？

> 原文:[https://www . geesforgeks . org/how-用法-portal-component-in-reactjs/](https://www.geeksforgeeks.org/how-to-use-portal-component-in-reactjs/)

门户组件将其子组件渲染到当前 DOM 层次结构之外的新*子树*中。【React 的 Material UI 有这个组件可供我们使用，非常容易集成。我们可以使用以下方法在 ReactJS 中使用门户组件。

**创建反应应用程序并安装模块。**

**步骤 1:** 使用以下命令创建一个 React 应用程序。

```jsx
npx create-react-app foldername
```

**步骤 2:** 在创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹。**

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装 **material-ui** 模块。

```jsx
npm install @material-ui/core
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from 'react';
import Portal from '@material-ui/core/Portal';

export default function App() {

  const [isVisible, setVisibility] = React.useState(false);
  const box = React.useRef(null);

  return (
    <div style={{ display: 'block', padding: 30, width: 500 }}>
      <h4>How to use Portal Component in ReactJS?</h4>
      <button type="button" onClick={() => {
        setVisibility(!isVisible)
      }}>
        {!isVisible ?
          'Mount the Children' :
          'Unmount the Children'}
      </button>
      <div style={{
        padding: 12,
        margin: 2,
        border: '2px solid',
      }}>
        Greetings from GeeksforGeeks
        {isVisible ? (
          <Portal container={box.current}>
            <span>Your Mounted Data is Here!!</span>
          </Portal>
        ) : null}
      </div>
      <div style={{
        padding: 12,
        margin: 2,
        border: '2px solid',
      }} ref={box} />
    </div>
  );
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序。

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出。

![](img/2d7cc031297a85da312405c5c09f4444.png)

**参考:**T2】https://material-ui.com/components/portal/