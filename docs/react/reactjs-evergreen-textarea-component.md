# 反应常绿植物区成分

> 原文:[https://www . geeksforgeeks . org/reactjs-evergreen-textarea-component/](https://www.geeksforgeeks.org/reactjs-evergreen-textarea-component/)

React Evergreen 是一个受欢迎的前端库，它有一组 React 组件来构建漂亮的产品，因为这个库是灵活的、合理的默认值和用户友好的。文本区域组件允许用户通过文本区域输入字段输入更长的内容。我们可以在 ReactJS 中使用以下方法来使用常青树文本区组件。

**Textarea 命题:**

*   **必需:**当设置为真时，textarea 元素是必需的。
*   **禁用:**当设置为真时，textarea 元素禁用。
*   **无效:**用于将 _only_ 文本输入的视觉样式设置为*无效*。
*   **拼写检查:**用于浏览器的原生拼写检查功能。
*   **语法:**用于允许语法浏览器扩展附加到后台文本区。
*   **占位符:**用于表示占位符文本。
*   **外观:**用于文本区的外观。
*   **宽度:**用于表示文本区域的宽度。
*   **类名:**用于将类名传递给按钮。

**TextareaField 道具:**

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
import { Textarea } from 'evergreen-ui'

export default function App() {

  // State for our summary of poem
  const [summary, setSummary] = React.useState('')

  return (
    <div style={{
      display: 'block', width: 700, paddingLeft: 30
    }}>
      <h4>ReactJS Evergreen Textarea Component</h4>
      <Textarea
        onChange={(e) => setSummary(e.target.value)}
        placeholder="Enter your summary of poem"
      /> <br></br>
      Summary: {summary}
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/23148b9803a9e9be5754f92199c237aa.png)****

******参考:**T2】https://evergreen.segment.com/components/textarea****