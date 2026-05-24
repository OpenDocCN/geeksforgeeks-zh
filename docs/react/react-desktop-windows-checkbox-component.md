# Reaction Desktop Windows 复选框组件

> Original: [https://www.geeksforgeeks.org/react-desktop-windows-checkbox-component/](https://www.geeksforgeeks.org/react-desktop-windows-checkbox-component/)

Reaction Desktop 是一个将原生桌面体验带到 Web 上的受欢迎的库。 该库提供MacOS和 Windows OS 组件。 复选框组件用于允许用户从给定选项中进行二元选择。 我们可以在 ReactJS 中使用以下方法来使用 Reaction Desktop Windows 复选框组件。

**复选框道具：**

*   **颜色：**用于设置复选框颜色。
*   **defaultValue：**表示默认输入值。
*   **defaultChecked：**表示是否默认勾选。
*   **隐藏：**用于设置零部件的可见性。
*   **标签：**用于为复选框添加标签。
*   **onChange：**它是复选框更改时触发的回调函数。
*   **主题：**它用于设置 UI 主题，然后该组件及其子元素使用该主题。

**创建 Reaction 应用程序并安装模块：**

*   **步骤 1：**使用以下命令创建 Reaction 应用程序：

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2：**创建项目文件夹(即 foldername**)后，**使用以下命令移动到该文件夹：

    ```jsx
    cd foldername
    ```

*   **步骤 3：**创建 ReactJS 应用程序后，使用以下命令安装所需的****模块：****

    ```jsx
    **npm install react-desktop**
    ```

******项目结构：**如下所示。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例：**现在在**App.js**文件中写下以下代码。 在这里，App 是我们编写代码的默认组件。****

## ****App.js****

```jsx
**import React from 'react'
import { Checkbox } from 'react-desktop/windows';

export default function App() {
  return (
    <div style={{
      display: 'block', width: 700, paddingLeft: 30
    }}>
      <h4>React-Desktop Checkbox Component</h4>
      <Checkbox
        label="Accept terms and conditions"
        onChange={() => alert("Accepted!")}
      />
    </div>
  );
}**
```

******运行应用程序的步骤：**使用以下命令从项目根目录运行应用程序：****

```jsx
**npm start**
```

******输出：**现在打开浏览器，转到***http://localhost:3000/***，您将看到以下输出：****

****![](img/99753d458a1ed8de1ed32c5b9fdba5ed.png)****

******引用：**[http://reactdesktop.js.org/docs/windows/checkbox](http://reactdesktop.js.org/docs/windows/checkbox)****