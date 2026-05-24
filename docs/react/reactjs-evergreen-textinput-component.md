# 重新获取常青文本输入组件

> 原文:[https://www . geeksforgeeks . org/reactjs-evergreen-text input-component/](https://www.geeksforgeeks.org/reactjs-evergreen-textinput-component/)

React Evergreen 是一个受欢迎的前端库，它有一组 React 组件来构建漂亮的产品，因为这个库是灵活的、合理的默认值和用户友好的。文本输入组件允许用户通过文本输入字段输入文本。我们可以在 ReactJS 中使用以下方法来使用长青文本输入组件。

**TextInput 命题:**

*   **必选:**设置为真时需要输入元素。
*   **禁用:**当设置为真时，输入元件禁用。
*   **无效:**用于将 _only_ 文本输入的视觉样式设置为*无效*。
*   **拼写检查:**用于浏览器的原生拼写检查功能。
*   **占位符:**用于表示占位符文本。
*   **外观:**用于文本输入的外观。
*   **宽度:**用于表示文本输入的宽度。
*   **类名:**用于将类名传递给按钮。

**文字表述场命题:**

*   **标签:**用于表示输入元素上方使用的标签。
*   **标签符:**用于表示标签上作为 htmlFor 道具传递的。
*   **必选:**用于表示标签后是否显示星号。
*   **描述:**定义标签下方和输入元素上方字段的可选描述。
*   **提示:**用于定义输入元素下的可选提示。
*   **验证消息:**用于显示验证消息。
*   **输入高度:**用于表示输入元素的高度。
*   **输入宽度:**用于表示输入宽度的宽度。

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
    **npm install evergreen-ui**
    ```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。****

## ****App.js****

```jsx
**import React from 'react'
import { TextInput } from 'evergreen-ui'

export default function App() {

  // State for Name
  const [name, setName] = React.useState('')

  return (
    <div style={{
      display: 'block', width: 700, paddingLeft: 30
    }}>
      <h4>ReactJS Evergreen TextInput Component</h4>
      <TextInput
        onChange={(e) => setName(e.target.value)}
        placeholder="Enter your name"
      /> <br></br>
      Name: {name}
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/174f5d5126e109ae03f8dca66eae62ed.png)****

******参考:**T2】https://evergreen.segment.com/components/text-input****