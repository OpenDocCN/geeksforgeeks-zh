# 重新获取长青搜索输入组件

> 原文:[https://www . geeksforgeeks . org/reactjs-evergreen-search input-component/](https://www.geeksforgeeks.org/reactjs-evergreen-searchinput-component/)

React Evergreen 是一个受欢迎的前端库，它有一组 React 组件来构建漂亮的产品，因为这个库是灵活的、合理的默认值和用户友好的。搜索输入组件允许用户通过在提供给用户的文本输入字段中输入来搜索。我们可以在 ReactJS 中使用以下方法来使用长青搜索输入组件。

**搜索输入道具:**这个不拿任何道具。

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
    **npm install evergreen-ui**
    ```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。****

## ****App.js****

```jsx
**import React from 'react'
import { SearchInput } from 'evergreen-ui'

export default function App() {

  return (
    <div style={{
      display: 'block', width: 700, paddingLeft: 30
    }}>
      <h4>ReactJS Evergreen SearchInput Component</h4>
      <SearchInput placeholder="Search anything..." />
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/3c992b063ba3bdbb79e3125890a2498b.png)****

******参考:**T2】https://evergreen.segment.com/components/search-input****