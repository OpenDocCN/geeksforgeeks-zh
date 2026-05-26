# 如何在 React.js 中创建自定义进度条组件？

> 原文：[https://www.geeksforgeeks.org/how-to-create-a-custom-progress-bar-component-in-react-js/](https://www.geeksforgeeks.org/how-to-create-a-custom-progress-bar-component-in-react-js/)

在本文中，我们将使用 React.js 创建一个自定义的可重用进度条组件。

## 先决条件

*   React 的基本知识
*   HTML/CSS 基础知识
*   React 中的内联样式

## `<Progressbar />` 组件应执行以下操作

1.  通过彩色条向用户直观地指示进度。
2.  以百分比的形式显示百分比。
3.  允许您通过 props 更改进度条的高度、宽度和背景颜色。

基本上，进度条由一个父 `div` 和一个子 `div` 组成。父 `div` 代表整个进度条，子 `div` 代表进度条的已完成部分，以及一个显示已完成百分比数字的 `span`。

### Props

*   `bgcolor`: 会改变进度条的背景颜色。
*   `progress`: 数值在 1 到 100 之间。
*   `height`: 用于改变进度条的高度。

## 创建 React 应用程序并安装模块

### 步骤 1
使用以下命令创建一个 React 应用程序：

```jsx
npx create-react-app progress_bar
```

### 步骤 2
创建项目文件夹（即文件夹名称）后，使用以下命令移动到该文件夹：

```jsx
cd Progress_bar
```

### 步骤 3
在 `components` 文件夹中添加一个 `ProgressBar.js` 文件，然后在 `App.js` 中导入进度条组件。

### 项目结构
如下图。

![文件夹结构](img/0646f2d51408ca4ce0a89a13a74831cc.png)

### 步骤 4
现在让我们在 `ProgressBar.js` 中创建进度条。

## ProgressBar.js

```jsx
import React from 'react'

const Progress_bar = ({bgcolor,progress,height}) => {

const Parentdiv = {
        height: height,
        width: '100%',
        backgroundColor: 'whitesmoke',
        borderRadius: 40,
        margin: 50
      }

const Childdiv = {
        height: '100%',
        width: `${progress}%`,
        backgroundColor: bgcolor,
       borderRadius:40,
        textAlign: 'right'
      }

const progresstext = {
        padding: 10,
        color: 'black',
        fontWeight: 900
      }

return (
    <div style={Parentdiv}>
      <div style={Childdiv}>
        <span style={progresstext}>{`${progress}%`}</span>
      </div>
    </div>
    )
}

export default Progress_bar;
```

### 步骤 5
让我们通过将进度条组件导入来渲染进度条组件。

## App.js

```jsx
import './App.css';
import Progressbar from './Component/Progress_bar';

function App() {
  return (
    <div className="App">
      <h3 className="heading">Progress Bar</h3>
      <Progressbar bgcolor="orange" progress='30' height={30} />
      <Progressbar bgcolor="red" progress='60' height={30} />
      <Progressbar bgcolor="#99ff66" progress='50' height={30} />
      <Progressbar bgcolor="#ff00ff" progress='85' height={30} />
      <Progressbar bgcolor="#99ccff" progress='95' height={30} />
    </div>
  );
}

export default App;
```

## 运行应用程序的步骤
从项目根目录使用以下命令运行应用程序：

```jsx
npm start
```

## 输出
现在打开浏览器，转到 `http://localhost:3000/`，会看到如下输出：

![React 进度条](img/8762e92a8404c63032119cde2a25e6db.png)