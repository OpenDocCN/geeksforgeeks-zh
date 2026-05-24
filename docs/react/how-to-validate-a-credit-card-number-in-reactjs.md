# 如何在 ReactJS 中验证信用卡号？

> 原文:[https://www . geeksforgeeks . org/如何验证信用卡号码 in-reactjs/](https://www.geeksforgeeks.org/how-to-validate-a-credit-card-number-in-reactjs/)

信用卡验证是每个应用程序中的一个重要步骤，目的是验证用户的信用卡号，以便应用程序在需要时可以继续支付过程。这可以使用 ReactJS 中的验证器模块来实现。以下示例显示了如何使用 ReactJS 应用程序中的 npm 模块验证用户输入的信用卡号并检查其是否有效。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app creditcardvalidatedemo
```

**步骤 2:** 创建项目文件夹(即**信用卡验证演示)后，**使用以下命令移动到该文件夹:

```jsx
cd creditcardvalidatedemo
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装**验证器**模块:

```jsx
npm install validator
```

**项目结构:**如下图

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**App.js:** 现在在 **App.js** 文件中写下以下代码。在这里，应用程序是我们的默认组件，我们已经编写了代码来使用基本的用户界面验证信用卡号。

## java 描述语言

```jsx
import React, { useState } from "react";
import validator from 'validator'

const App = () => {

  const [errorMessage, setErrorMessage] = useState('')

  const validateCreditCard = (value) => {

    if (validator.isCreditCard(value)) {
      setErrorMessage('Valid CreditCard Number')
    } else {
      setErrorMessage('Enter valid CreditCard Number!')
    }
  }

  return (
    <div style={{
      marginLeft: '200px',
    }}>
      <pre>
        <h2>Validating CreditCard in ReactJS</h2>
        <span>Enter CreditCard: </span><input type="text" 
        onChange={(e) => validateCreditCard(e.target.value)}></input> <br />
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

*   如果用户输入如下所示的无效信用卡号，将输出以下内容:

![](img/a2bb500a961dea5c2ab728757b1c4c2b.png)

*   如果用户输入如下所示的有效信用卡号，将输出以下内容:

![](img/ebab9d2099072790b3bb0a842d245756.png)