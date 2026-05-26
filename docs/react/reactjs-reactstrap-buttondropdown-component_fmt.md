# Reactstrap ButtonDropdown 组件

> 原文: [https://www.geeksforgeeks.org/reactjs-reactstrap-buttondropdown-component/](https://www.geeksforgeeks.org/reactjs-reactstrap-buttondropdown-component/)

`Reactstrap`是一个流行的前端库，可以轻松使用 React Bootstrap 4 组件。该库包含 Bootstrap 4 的无状态 React 组件。ButtonDropdown 组件用于渲染组或分割按钮下拉引导组件。我们可以在 ReactJS 中使用以下方法来使用 Reactstrap ButtonDropdown 组件。

## ButtonDropdown Props

*   `disabled`: 表示组件是否禁用。
*   `direction`: 用于表示左、右等元素的方向。
*   `group`: 表示是否应用 `group` 类。
*   `isOpen`: 表示是否处于开启状态。
*   `tag`: 用于表示该组件的标签道具。
*   `toggle`: 是在该组件切换时触发的回调函数。

## DropdownToggle Props

*   `caret`: 用于指示是否应用脱字符号类。
*   `color`: 用于表示部件的颜色。
*   `disabled`: 表示组件是否禁用。
*   `onClick`: 是点击该组件触发的回调函数。
*   `data-toggle`: 表示是否应用 `data-toggle` 类。
*   `aria-haspopup`: 用于表示是否应用 `aria-haspopup` 类。

## 创建 React 应用程序并安装模块

**步骤 1:** 使用以下命令创建一个 React 应用程序:
```jsx
npx create-react-app foldername
```

**步骤 2:** 在创建项目文件夹（即 `foldername`）后，使用以下命令移动到该文件夹:
```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的 `reactstrap` 和 `bootstrap` 模块:
```jsx
npm install reactstrap bootstrap
```

**项目结构:** 如下图。
![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)
项目结构

**示例 1:** 现在在 `App.js` 文件中写下以下代码。在这里，`App` 是我们编写代码的默认组件。

## JavaScript 代码

```jsx
import React from 'react'
import 'bootstrap/dist/css/bootstrap.min.css';
import {
    DropdownMenu, DropdownItem,
    ButtonDropdown, DropdownToggle
} from "reactstrap"

function App() {
    // ButtonDropdown open state
    const [dropdownOpen, setOpen] = React.useState(false);

    return (
        <div style={{
            display: 'block', width: 700, padding: 30
        }}>
            <h4>ReactJS Reactstrap ButtonDropdown Component</h4>
            <ButtonDropdown toggle={() => { setOpen(!dropdownOpen) }}
                isOpen={dropdownOpen}>
                <DropdownToggle className="bg-primary" caret>
                    Sample Button Dropdown
                </DropdownToggle>
                <DropdownMenu>
                    <DropdownItem header>Numeric Characters
                    </DropdownItem>
                    <DropdownItem>One</DropdownItem>
                    <DropdownItem>Two</DropdownItem>
                    <DropdownItem>Three</DropdownItem>
                    <DropdownItem>Four</DropdownItem>
                    <DropdownItem>Five</DropdownItem>
                    <DropdownItem>Six</DropdownItem>
                    <DropdownItem>Seven</DropdownItem>
                    <DropdownItem>Eight</DropdownItem>
                    <DropdownItem>Nine</DropdownItem>
                    <DropdownItem>Zero</DropdownItem>
                </DropdownMenu>
            </ButtonDropdown>
        </div >
    );
}

export default App;
```