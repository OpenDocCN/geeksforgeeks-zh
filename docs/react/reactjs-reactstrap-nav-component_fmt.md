# 反应堆捕捉导航组件

> 原文: [https://www.geeksforgeeks.org/reactjs-reactstrap-nav-component/](https://www.geeksforgeeks.org/reactjs-reactstrap-nav-component/)

Reactstrap 是一个流行的前端库，易于使用 React Bootstrap 4 组件。该库包含引导 4 的无状态反应组件。导航组件允许用户提供各种形式导航菜单的列表。我们可以在 ReactJS 中使用以下方法来使用 ReactJS Reactstrap 导航组件。

**导航道具:**

*   `tabs`: 用于指示是否对其应用制表符样式。
*   `pills`: 表示药丸导航。
*   `card`: 表示是否应用卡片样式。
*   `justified`: 它使导航项目填充所有可用的宽度。
*   `fill`: 它使导航项目按比例填充所有可用宽度。
*   `vertical`: 表示是否应用垂直对齐。
*   `horizontal`: 表示是否应用水平对齐。
*   `navbar`: 用于为导航条中使用的路线设置样式。
*   `tag`: 用于传入自定义元素使用。

**导航项道具:**

*   `tag`: 用于传入自定义元素使用。
*   `active`: 用于将激活状态类应用于该组件。

**插入符:**

*   `disabled`: 用于将 disabled 状态类应用于该组件。
*   `active`: 用于将激活状态类应用于该组件。
*   `tag`: 用于传入自定义元素使用。
*   `innerRef`: 用于获取对 DOM 元素的引用。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 在创建项目文件夹(即文件夹名)后，使用以下命令将移动到该文件夹:

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的模块:

```jsx
npm install reactstrap bootstrap
```

**项目结构:** 如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例 1:** 现在在 `App.js` 文件中写下以下代码。在这里，我们使用了药丸道具，并显示了水平对齐的导航。

```jsx
import React from 'react'
import 'bootstrap/dist/css/bootstrap.min.css';
import { Nav, NavItem, NavLink } from "reactstrap"

function App() {
    return (
        <div style={{
            display: 'block', width: 700, padding: 30
        }}>
            <h4>ReactJS Reactstrap Nav Component</h4>
            <Nav pills>
                <NavItem>
                    <NavLink href="#" active>Dashboard</NavLink>
                </NavItem>
                <NavItem>
                    <NavLink href="#">Login</NavLink>
                </NavItem>
                <NavItem>
                    <NavLink href="#">Signup</NavLink>
                </NavItem>
                <NavItem>
                    <NavLink disabled href="#">About us</NavLink>
                </NavItem>
            </Nav>
        </div >
    );
}

export default App;
```