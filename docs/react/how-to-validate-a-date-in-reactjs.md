# 如何在 ReactJS 中验证日期？

> 原文:[https://www . geeksforgeeks . org/如何验证重新认证日期/](https://www.geeksforgeeks.org/how-to-validate-a-date-in-reactjs/)

数据验证是每个应用程序中的一个重要步骤，以便验证用户输入的数据，这些数据可用于计算出生日期或任何其他用途。这可以使用 ReactJS 中的验证器模块来实现。以下示例显示了如何使用 ReactJS 应用程序中的 npm 模块验证用户输入的数据并检查其是否有效。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app datevalidatedemo
```

**步骤 2:** 创建项目文件夹后，即 **datevalidatedemo，**使用以下命令移动到该文件夹:

```jsx
cd datevalidatedemo
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装**验证器**模块:

```jsx
npm install validator
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**App.js:** 现在在 **App.js** 文件中写下以下代码。在这里，应用程序是我们的默认组件，我们已经编写了代码来用基本的用户界面验证日期。

## java 描述语言

```jsx
import React, { useState } from "react";
import validator from 'validator'

const App = () => {

  const [errorMessage, setErrorMessage] = useState('')

  const validateDate = (value) => {

    if (validator.isDate(value)) {
      setErrorMessage('Valid Date :)')
    } else {
      setErrorMessage('Enter Valid Date!')
    }
  }

  return (
    <div style={{
      marginLeft: '200px',
    }}>
      <pre>
        <h2>Validating Date in ReactJS</h2>
        <span>Enter Date: </span><input type="text" 
        onChange={(e) => validateDate(e.target.value)}></input> <br />
        <span style={{
          fontWeight: 'bold',
          color: 'red',
        }}>{errorMessage}</span>
      </pre>
    </div>
  );
}

export default App
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**

*   如果用户输入如下所示的无效日期，将输出以下内容:

![](img/12a3336b0701f078d55b27a9729e7b3a.png)

*   如果用户输入如下所示的有效日期，则输出如下:

![](img/bfc98fd87bf74ae6182606660a8333c6.png)