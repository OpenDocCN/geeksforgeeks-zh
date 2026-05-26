# ReactJS Reactstrap 分页组件

> 原文: [https://www.geeksforgeeks.org/reactjs-reactstrap-pagination-component/](https://www.geeksforgeeks.org/reactjs-reactstrap-pagination-component/)

Reactstrap 是一个流行的前端库，易于使用 React Bootstrap 4 组件。该库包含引导 4 的无状态反应组件。分页组件允许用户在网站或应用程序之间轻松切换页面。我们可以在 ReactJS 中使用以下方法来使用 ReactJS Reactstrap 分页组件。

## 页码命题

*   `children`: 用于将 children 元素传递给这个组件。
*   `className`: 用于表示该组件的类名。
*   `listClassName`: 用于表示列表样式的类名。
*   `cssModule`: 用来表示造型用的 CSS 模块。
*   `size`: 用于表示构件的尺寸。
*   `tag`: 用于表示该组件的标签。
*   `listTag`: 用于表示 ol、ul 等列表标签。
*   `ariaLabel`: 用于表示咏叹调标签属性。

## 页码编排的命题

*   `active`: 用于将分页项目设置为激活状态。
*   `children`: 用于将 children 元素传递给这个组件。
*   `className`: 用于表示该组件的类名。
*   `cssModule`: 用来表示造型用的 CSS 模块。
*   `disabled`: 表示分页项是否禁用。
*   `tag`: 用于表示该组件的标签。

## 页面链接前缀

*   `children`: 用于将 children 元素传递给这个组件。
*   `className`: 用于表示该组件的类名。
*   `cssModule`: 用来表示造型用的 CSS 模块。
*   `next`: 表示是否显示下一步按钮。
*   `previous`: 表示是否显示上一个按钮。
*   `first`: 表示是否显示第一个按钮。
*   `last`: 表示是否显示最后一个按钮。
*   `tag`: 用于表示该组件的标签。
*   `ariaLabel`: 用于表示咏叹调标签属性。

## 创建反应应用程序并安装模块

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 在创建项目文件夹(即文件夹名 `foldername`)后，使用以下命令将移动到该文件夹:

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

**示例 1:** 现在在 `App.js` 文件中写下以下代码。这里，我们展示了不带上一个和下一个按钮的分页。

### java 描述语言

```jsx
import React from 'react'
import 'bootstrap/dist/css/bootstrap.min.css';
import { Pagination, PaginationItem, PaginationLink } from "reactstrap"

function App() {

return (
        <div style={{
            display: 'block', width: 700, padding: 30
        }}>
            <h4>ReactJS Reactstrap Pagination Component</h4>
            <Pagination>
                <PaginationItem>
                    <PaginationLink href="#">1</PaginationLink>
                </PaginationItem>
                <PaginationItem>
                    <PaginationLink href="#">2</PaginationLink>
                </PaginationItem>
                <PaginationItem>
                    <PaginationLink href="#">3</PaginationLink>
                </PaginationItem>
                <PaginationItem>
                    <PaginationLink href="#">4</PaginationLink>
                </PaginationItem>
                <PaginationItem>
                    <PaginationLink href="#">5</PaginationLink>
                </PaginationItem>
            </Pagination>
        </div >
    );
}

export default App;
```