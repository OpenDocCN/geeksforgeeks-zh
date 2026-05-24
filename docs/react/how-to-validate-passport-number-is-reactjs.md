# 如何验证护照号是 ReactJS？

> 原文:[https://www . geeksforgeeks . org/如何验证-passport-number-is-reactjs/](https://www.geeksforgeeks.org/how-to-validate-passport-number-is-reactjs/)

**护照号码** r 验证是验证用户护照号码的重要步骤。以下示例显示了如何使用 ReactJS 中的 npm 模块验证用户的护照号码。

**语法:**

```jsx
isPassportNumber(str, countryCode)
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **字符串:**是字符串类型的输入值。
*   **国家代码**:是该护照的国家代码，例如:‘AM’‘US’‘IN’等。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 在创建项目文件夹(即文件夹名**)后，使用以下命令将**移动到该文件夹:

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装**验证器**模块:

```jsx
npm install validator
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**App.js:** 现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## java 描述语言

```jsx
import React, { useState } from "react";
import validator from 'validator'

const App = () => {

  const [errorMessage, setErrorMessage] = useState('')

  const validate = (textInput) => {

    if (validator.isPassportNumber(textInput,'IN')) {
      setErrorMessage('Is Valid Passport Number')
    } else {
      setErrorMessage('Is Invalid Passport Number')
    }
  }

  return (
    <div style={{
      marginLeft: '200px',
    }}>
      <pre>
        <h2>Validate Passport Number in ReactJS</h2>
        <span>Enter Passport Number: </span><input type="text"
          onChange={(e) => validate(e.target.value)}></input> <br />
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

*   如果用户输入了无效的护照号码，输出如下。

![](img/4b3cde902cd05857bc9e08c39f1174d4.png)

*   如果用户输入有效的护照号码，输出如下。

![](img/7eb8365487ed71b03551714d5d1be6b2.png)