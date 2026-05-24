# React.js 构造函数()方法

> Original: [https://www.geeksforgeeks.org/react-js-constructor-method/](https://www.geeksforgeeks.org/react-js-constructor-method/)

构造函数是当我们从该类创建对象时自动调用的方法。 它可以管理初始初始化任务，例如默认某些对象属性或对传入的参数进行健全性测试。 简单地说，构造函数是帮助创建对象的方法。

构造函数在反应方面没有什么不同。 这可以将事件处理程序连接到组件和/或初始化组件的本地状态。 在挂载组件之前，会启动构造函数()，与 Reaction 中的大多数内容一样，它有几条规则，您可以在使用它们时遵循这些规则。

*   **第一步：**使用 this.props 之前调用 super.props

    由于构造函数的性质，*this.props*对象不能直接从 GATE 访问，这可能会导致错误。 此构造函数将引发错误：

    ```jsx
    constructor() {
     console.log(this.props);
    }
    ```

    相反，我们将道具的值从构造函数()传递给 Super()函数：

    ```jsx
    constructor(props) {
     super(props);
     console.log(this.props);
    }
    ```

    调用 Super()函数时，会调用父类构造函数，在 Reaction 的情况下，父类构造函数是 React.Component。

*   **步骤 2：**不要在构造函数()内调用 setState()

    组件的构造函数是设置组件初始状态的理想位置。 必须直接设置初始状态，而不是像在类中的其他方法中那样使用 setState()：

    ```jsx
    constructor(props) {
     super(props);

     this.state = {
       name 'kapil',
       age: 22,
     };
    }
    ```

    唯一可以像这样直接分配本地状态的地方是构造函数。 相反，您应该依赖于组件中其他位置的 setState()。

*   **步骤 3：**避免将 this.props 中的值赋给 this.state

    在构造函数中设置初始组件状态时，应尽量避免设置属性中的值。 我们可以做到以下几点：

    ```jsx
    constructor(props) {
     super(props);

     this.state = {
       name: props.name,
     };
    }
    ```

    以后不允许使用 setState()更改属性。 您可以通过命名 this.pros.name 来轻松地在代码中直接引用该属性，而不是将该属性直接分配给州。

*   **第四步：**在一个地方绑定所有事件

    我们可以很容易地在构造函数中绑定您的事件处理程序：

    ```jsx
    constructor(props) {
     super(props);

     this.state = {
       // Sets that initial state
     };

     // Our event handlers
     this.onClick = this.onClick.bind(this);
     this.onKeyUp = this.onKeyUp.bind(this);
     // Rest Code
    }
    ```

**创建 Reaction 应用程序：**

*   **步骤 1：**使用以下命令创建 Reaction 应用程序。

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2：**创建项目文件夹(即 Foldername)后，使用以下命令移动到该文件夹。

    ```jsx
    cd foldername
    ```

**项目结构：**如下所示。

![](img/61c6f1343b04abacfcac2db8b7a3d996.png)

**示例：**现在在**App.js**文件中写下以下代码。 这里，App 是我们编写代码的默认组件。下面的示例介绍了构造函数演示。

## App.js

```jsx
import React, { Component } from 'react';

class App extends Component {

  constructor(props) {

    // Calling super class constructor
    super(props);

    // Creating state
    this.state = {
      data: 'My name is User'
    }

    // Binding event handler
    this.handleEvent = this.handleEvent.bind(this);
  }

  handleEvent() {
    console.log(this.props);
  }

  render() {
    return (
      <div >
        <input type="text" value={this.state.data} />
        <br></br> <br></br>
        <button onClick={this.handleEvent}>Please Click</button>
      </div>
    );
  }
}

export default App;
```

**运行应用程序的步骤：**从项目的根目录运行应用程序，使用以下命令

```jsx
npm start
```

发帖主题：Re：Колибри0.7.0

![](img/0ba7bb249e72ca7e96e4c1feae8f301f.png)