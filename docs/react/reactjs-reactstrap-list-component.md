# 反应堆捕捉列表组件

> 原文:[https://www . geeksforgeeks . org/reactjs-reatstrap-list-component/](https://www.geeksforgeeks.org/reactjs-reactstrap-list-component/)

Reactstrap 是一个流行的前端库，易于使用 React Bootstrap 4 组件。该库包含引导 4 的无状态反应组件。列表组件允许用户显示列表。我们可以在 ReactJS 中使用以下方法来使用 ReactJS Reactstrap 陷阱列表组件。

**列出道具:**

*   **标签:**用于表示该组件的标签。
*   **类名:**用于表示造型的类名。
*   **cssModule:** 用来表示造型用的 CSS 模块。
*   **类型:**用于表示列表的类型。

**上市命题:**

*   **标签:**用于表示该组件的标签。
*   **类名:**用于表示造型的类名。
*   **cssModule:** 用来表示造型用的 CSS 模块。

**创建反应应用程序并安装模块:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序:

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 在创建项目文件夹(即文件夹名**)后，使用以下命令将**移动到该文件夹:

    ```jsx
    cd foldername
    ```

*   **步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的****模块:****

    ```jsx
    **npm install reactstrap bootstrap**
    ```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例 1:** 现在在 **App.js** 文件中写下以下代码。这里，我们展示了列表组件和列表项目组件。****

## ****App.js****

```jsx
**import React from 'react'
import 'bootstrap/dist/css/bootstrap.min.css';
import { ListInlineItem, List } from "reactstrap"

function App() {
    return (
        <div style={{
            display: 'block', width: 700, padding: 30
        }}>
            <h4>ReactJS Reactstrap List Component</h4>
            <List type="inline">
                <ListInlineItem>Sample Item 1</ListInlineItem>
                <ListInlineItem>Sample Item 2</ListInlineItem>
                <ListInlineItem>Sample Item 3</ListInlineItem>
                <ListInlineItem>Sample Item 4</ListInlineItem>
                <ListInlineItem>Sample Item 5</ListInlineItem>
            </List>
        </div>
    );
}

export default App;**
```