# 在 ReactJS 中使用样式化的 API

> 原文:[https://www.geeksforgeeks.org/using-styled-api-in-reactjs/](https://www.geeksforgeeks.org/using-styled-api-in-reactjs/)

[ReactJS](https://www.geeksforgeeks.org/reactjs/) 中的样式化组件是一个 JS 中的 CSS 库，可以用于更好的 UI 设计。这个应用编程接口允许我们创建一个样式化的组件并应用所有的样式属性。为了在反应中使用风格化的应用编程接口，我们需要安装风格化的组件。

**先决条件:**

*   [反应的基础知识](https://www.geeksforgeeks.org/reactjs/)
*   已创建 [ReactJS](https://www.geeksforgeeks.org/reactjs/) 应用程序

#### 在 ReactJS 中使用样式化组件的步骤:

**第一步:**在继续下一步之前，首先我们必须通过在您的项目目录中运行以下命令，借助于您的 *src* 文件夹中的终端，或者您也可以在您的项目文件夹中的 Visual Studio Code 的终端中运行该命令来安装样式化的组件。

```jsx
npm install --save styled-components
```

**步骤 2:** 安装完模块后，现在打开您的 App.js 文件，该文件位于项目目录中的 *src* 文件夹下。

**第 3 步:**现在导入 React 和 styled 模块。

**第 4 步:**在你的 App.js 文件中，添加这个代码片段来导入 React 和 styled 模块。

```jsx
import React from 'react';
import styled from 'styled-components';
```

下面是一个示例程序来说明样式化组件的使用:

**示例 1:** 将按钮的背景颜色更改为绿色。

**App.js:**

## java 描述语言

```jsx
import React from 'react';

// Importing styled from styled-components
import styled from 'styled-components';

// Importing the background-color of your 
// choice to the button using css
// Button component that will render an <a> 
// tag with some styles using styled.
const Button = styled.a`
  background-color:green;
  color: white;
  padding: 1rem 2rem;
  margin-top:100px;
  width: 150px;
  display: block;
`
const App = () => {
  return (
    <center><Button>GeeksforGeeks</Button></center>
  )
}

export default App;
```

**输出:**

![](img/8f691e83d04c7671f7690c0af340d278.png)

**示例 2** :给按钮添加边框。

**App.js:**

## java 描述语言

```jsx
import React from 'react';

// Importing styled from styled components
import styled from 'styled-components';

// Importing the background-color of your 
// choice to the button using css
// Button component that will render an <a>
// tag with some styles using styled.
const Button = styled.a`
  background-color:green;
  color: white;
  padding: 1rem 2rem;
  margin-top:100px;
  width: 150px;
  display: block;
  border:8px solid black;
`
const App = () => {
  return (
    <center><Button>GeeksforGeeks</Button></center>
  )
}

export default App;
```

**输出:**

![](img/18abd923b1d8605da8c137b80164efb4.png)

因此，使用上述步骤，我们可以使用样式化组件来导入和更改 [React](https://www.geeksforgeeks.org/react-js-introduction-working/) 中组件的样式。