# 重新获取 Onsen 用户界面组件

> 原文:[https://www . geesforgeks . org/reactjs-onsen-ui-col-component/](https://www.geeksforgeeks.org/reactjs-onsen-ui-col-component/)

ReactJS Onsen-UI 是一个受欢迎的前端库，具有一组 React 组件，旨在以一种美观高效的方式开发 HTML5 混合和移动网络应用程序。Col 组件提供了一种在网格系统中表示 Col 的方式，用于以一列的形式显示数据。我们可以在 ReactJS 中使用以下方法来使用 Onsen-UI Col 组件。

**Col 道具:**

*   **垂直对齐:**是垂直对齐的短手属性。
*   **宽度:**用于表示柱的宽度。

**创建反应应用程序并安装模块:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序:

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

    ```jsx
    cd foldername
    ```

*   **步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的****模块:****

    ```jsx
    **npm install onsenui react-onsenui** 
    ```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。****

## ****App.js****

```jsx
**import React from 'react';
import 'onsenui/css/onsen-css-components.css';
import { Row, Col } from 'react-onsenui';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 500, paddingLeft: 30
    }}>
      <h6>ReactJS Onsen-UI Col Component</h6>
      <Row style={{ backgroundColor: 'lightblue' }}>
        <Col style={{ backgroundColor: 'lightblue', padding: 10 }}>
          1st Column Content</Col>
        <Col style={{ backgroundColor: 'lightgray', padding: 10 }}>
          2nd Column Content</Col>
        <Col style={{ backgroundColor: 'lightblue', padding: 10 }}>
          3rd Column Content</Col>
      </Row>
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/d16d833adbee8108f6c54023665a7dcf.png)****

******参考:**[https://onsen . io/v2/API/reac/col . html](https://onsen.io/v2/api/react/Col.html)****