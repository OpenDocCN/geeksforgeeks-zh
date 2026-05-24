# 重新连接 Onsen UI 开关组件

> 原文:[https://www . geesforgeks . org/reactjs-onsen-ui-switch-component/](https://www.geeksforgeeks.org/reactjs-onsen-ui-switch-component/)

ReactJS Onsen-UI 是一个受欢迎的前端库，具有一组 React 组件，旨在以一种美观高效的方式开发 HTML5 混合和移动网络应用程序。开关组件用于 切换单个设置的状态开或关。我们可以在 ReactJS 中使用以下方法来使用 Onsen-UI 开关组件。

**切换道具:**

*   **onChange :** 是当开关的值发生变化时触发的回调函数。
*   **已检查:**表示开关是否检查。
*   **禁用:**用于指定开关是否禁用。
*   **输入:**用于指定内部<输入>元素的“Id”属性。

**预设修改器:**

*   **材质:**用于显示材质设计开关。

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
import { Switch } from 'react-onsenui';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 500, paddingLeft: 30
    }}>
      <h6>ReactJS Onsen-UI Switch Component</h6>
      Switch
      <Switch
        modifier='material'
        onChange={(e) => { console.log(e) }}
      />
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/6b2a2b7190c83e2d08ea77a19860b587.png)****

******参考:**T2】https://onsen.io/v2/api/react/Switch.html****