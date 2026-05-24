# reactjsreatstrap 输入组组件

> 原文:[https://www . geeksforgeeks . org/reactjs-reatstrap-input group-component/](https://www.geeksforgeeks.org/reactjs-reactstrap-inputgroup-component/)

Reactstrap 是一个流行的前端库，易于使用 React Bootstrap 4 组件。该库包含引导 4 的无状态反应组件。输入组组件提供了一种在输入的任一侧或两侧放置一个附件或按钮的方法。我们可以在 ReactJS 中使用以下方法来使用 ReactJS Reactstrap InputGroup 组件。

**输入组道具:**

*   **标签:**用于表示该组件的标签。
*   **尺寸:**用于表示该部件的尺寸。
*   **类名:**用于表示造型的类名。

**InputGroupAddOn Props:**

*   **标签:**用于表示该组件的标签。
*   **附加类型:**用于表示附加类型，如前置或追加。
*   **类名:**用于表示造型的类名。

**input group button proposs:**

*   **标签:**用于表示该组件的标签。
*   **附加类型:**用于表示附加类型，如前置或追加。
*   **children:** 用于表示该组件的 children 元素。
*   **groupClassName:** 用于表示该组件的组类名。
*   **组属性:**用于表示该组件的组属性。
*   **类名:**用于表示造型的类名。

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
    **npm install reactstrap bootstrap**
    ```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例 1:** 现在在 **App.js** 文件中写下以下代码。这里，我们展示了带有文本字段类型输入字段的输入组组件。****

## ****App.js****

```jsx
**import React from 'react'
import 'bootstrap/dist/css/bootstrap.min.css';
import {
    Input, InputGroup,
    InputGroupText, InputGroupAddon
} from 'reactstrap';

function App() {

    return (
        <div style={{
            display: 'block', width: 550, padding: 30
        }}>
            <h5>ReactJS Reactstrap InputGroup Component</h5>
            <InputGroup>
                <InputGroupAddon addonType="prepend">
                    <InputGroupText>Detail</InputGroupText>
                </InputGroupAddon>
                <Input placeholder="Enter your username" />
            </InputGroup>
        </div >
    );
}

export default App;**
```