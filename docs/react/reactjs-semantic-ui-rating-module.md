# 重新获取语义用户界面评分模块

> 原文:[https://www . geeksforgeeks . org/reactjs-semantic-ui-rating-module/](https://www.geeksforgeeks.org/reactjs-semantic-ui-rating-module/)

语义用户界面是一个现代框架，用于为网站开发无缝设计，它给用户一个轻量级的组件体验。它使用预定义的 CSS、JQuery 语言来整合到不同的框架中。

在本文中，我们将了解如何在 ReactJS 语义用户界面中使用评级模块。评级模块用于显示用户给出的评级。

**属性:**

*   **星级:**我们可以用星级图标来评定。
*   **心脏:**我们可以使用心脏图标进行评级。
*   **可清除:**我们可以通过点击来清除评级。
*   **禁用:**该属性用于禁用等级。
*   **受控:**我们可以作为受控部件进行评级。
*   **onRate 回调:**是评级变动触发的回调函数。

**语法:**

```jsx
<rating />
```

**创建反应应用程序并安装模块:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序。

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹。

    ```jsx
    cd foldername
    ```

*   **第三步:**在给定的目录下安装语义 UI。

    ```jsx
     npm install semantic-ui-react semantic-ui-css
    ```

**项目结构**:如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

**运行应用程序的步骤:**使用以下命令从项目的根目录运行应用程序。

```jsx
npm start
```

**示例 1:** 这是展示如何使用 ReactJS 语义 UI 评级模块来使用评级模块的基本示例。

## App.js

```jsx
import React from 'react'
import { Rating } from 'semantic-ui-react'

const styleLink = document.createElement("link");
styleLink.rel = "stylesheet";
styleLink.href = 
"https://cdn.jsdelivr.net/npm/semantic-ui/dist/semantic.min.css";
document.head.appendChild(styleLink);

const btt = () => 
<div>
  <br/>
    <Rating icon='star' defaultRating={5} 
            maxRating={8} size='huge' clearable/>
</div>

export default btt
```

**输出:**

![](img/c45b031f99d32871cac888665fa5251a.png)

**示例 2:** 在本例中，我们使用 ReactJS 语义 UI 评级模块显示了评级模块中的禁用属性。

## App.js

```jsx
import React from 'react'
import { Rating } from 'semantic-ui-react'

const styleLink = document.createElement("link");
styleLink.rel = "stylesheet";
styleLink.href = 
"https://cdn.jsdelivr.net/npm/semantic-ui/dist/semantic.min.css";
document.head.appendChild(styleLink);

const btt = () => 
<div>
  <br/>
    <Rating icon='star' defaultRating={5} 
            maxRating={8} size='huge' disabled/>
</div>

export default btt
```

**输出:**

![](img/e19fe107ef7b7d0cf9c0f6b1cfadca9f.png)

**参考:**T2】https://react.semantic-ui.com/modules/rating