# 重新获取 Onsen UI 快速拨号项组件

> 原文:[https://www . geeksforgeeks . org/reactjs-onsen-ui-speed dial item-component/](https://www.geeksforgeeks.org/reactjs-onsen-ui-speeddialitem-component/)

ReactJS Onsen-UI 是一个受欢迎的前端库，具有一组 React 组件，旨在以一种美观高效的方式开发 HTML5 混合和移动网络应用程序。快速拨号项目组件允许用户定义项目，然后将其传递给快速拨号组件。我们可以在 ReactJS 中使用以下方法来使用 Onsen-UI SpeedDialItem 组件。

**高速拨号项目道具：**

*   **修饰词:**用于快速拨号的外观。
*   **onClick:** 是一个按钮一旦被点击就会被调用的函数。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的****模块:****

```jsx
**npm install onsenui react-onsenui** 
```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。****

## ****java 描述语言****

```jsx
**import React from 'react';
import 'onsenui/css/onsen-css-components.css';
import { SpeedDial, SpeedDialItem, Fab, Icon } from 'react-onsenui';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 500, paddingLeft: 30
    }}>
      <h6>ReactJS Onsen-UI SpeedDialItem Component</h6>
      <SpeedDial direction='right' position='left bottom'>
        <Fab><Icon size={50} style={{ verticalAlign: 'middle' }} /></Fab>
        <SpeedDialItem 
        onClick={() => { alert('1st Item Clicked!') }}>1</SpeedDialItem>
        <SpeedDialItem 
        onClick={() => { alert('2nd Item Clicked!') }}>2</SpeedDialItem>
      </SpeedDial>
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/7233195049bda050035e510d37863db3.png)****

******参考:**[https://onsen . io/v2/API/reac/speedy dial item . html](https://onsen.io/v2/api/react/SpeedDialItem.html)****