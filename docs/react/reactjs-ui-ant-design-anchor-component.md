# 重新获取用户界面蚂蚁设计锚组件

> 原文:[https://www . geeksforgeeks . org/reactjs-ui-ant-design-anchor-component/](https://www.geeksforgeeks.org/reactjs-ui-ant-design-anchor-component/)

蚂蚁设计库预建了这个组件，也很容易集成。锚组件用于允许 h 超链接滚动到一个页面 。当我们想要在页面上显示 锚定超链接并允许用户轻松在它们之间跳转时，有用的是。我们可以在 ReactJS 中使用以下方法来使用 Ant 设计锚组件。

**主播道具:**

*   **词缀:**用于表示 Anchor 的固定模式。
*   **边界:**用于绑定锚点区域的距离。
*   **getContainer:** 是获取滚动容器的函数。
*   **getCurrentAnchor:** 用于自定义锚点高亮。
*   **偏移量:**计算滚动位置时，用于表示从顶部偏移的像素。
*   **showInkInFixed:** 表示词缀设置为 false 时是否显示墨球。
*   **目标偏移量:**用于表示锚点滚动偏移量。
*   **onChange:** 是在锚点链接改变时触发的回调函数。
*   **onClick:** 是一个回调函数，用来设置处理点击事件的处理程序。

**链接道具:**

*   **href:** 用来表示超链接的目标。
*   **目标:**用于指定链接的 URL 在哪里显示。
*   **标题:**用于定义超链接的内容。

**创建反应应用程序并安装模块:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序:

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

    ```jsx
    cd foldername
    ```

*   **步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的模块:

    ```jsx
    npm install antd
    ```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from 'react'
import "antd/dist/antd.css";
import { Anchor } from 'antd';

const { Link } = Anchor;

export default function App() {
  return (
    <div style={{
      display: 'block', width: 700, padding: 30, height: 1000,
    }}>
      <h4>ReactJS Ant-Design Anchor Component</h4>
      <Anchor>
        <Link href="#" title="Course Link" />
        <Link href="#" title="Exam Link">
          <Link href="#" title="Study Material" />
          <Link href="#" title="Exam Prepration" />
          <Link href="#" title="Test Link" />
        </Link>
      </Anchor>
    </div>
  );
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/1324867b6a3da05e1fb1f19dea5d4b2d.png)

**参考:**T2】https://ant.design/components/anchor/