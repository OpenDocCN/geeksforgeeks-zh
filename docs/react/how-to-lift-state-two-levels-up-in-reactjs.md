# 如何在 ReactJS 中提升状态二级？

> 原文:[https://www . geeksforgeeks . org/如何提升状态-两级提升-in-reactjs/](https://www.geeksforgeeks.org/how-to-lift-state-two-levels-up-in-reactjs/)

我们希望将状态提升两个级别，这样当事件发生在较低级别组件时，它应该会影响状态的两个级别。例如，有三个组件 X，Y，z。X 是组件 Y 的父组件，Y 是组件 z 的父组件。

当组件 Z 中发生某个事件时，它应该会影响组件 X 的状态，组件 X 从组件 Z 向上两级。为此，我们必须将一个函数作为道具从组件 X 传递给组件 Y，然后组件 Y 将该函数传递给组件 X，这样组件 X 就可以调用该函数并更改组件 X 的状态

**示例:**

*   **X 状态**

    ```jsx
    this.state={ stateA: "whatever"}
    ```

*   **X 中的功能:**

    ```jsx
    setStateX(newValue){
       this.setState({stateA: newValue});
    }
    ```

*   现在把它作为道具传给 Y

    ```jsx
    <Y setStateX={this.setStateX} />
    ```

*   **In Y:**

    ```jsx
    <Z setStateX={this.props.setStateX} />
    ```

*   **In Z:**

    ```jsx
    this.props.setStateX("new value of stateX");
    ```

调用函数设置 x 的状态。

**创建反应应用程序:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹:

```jsx
cd foldername
```

**项目结构:**如下图。

![](img/6abc9b65250f4f9334477e16c5fa4ec4.png)

**示例:**

## App.js

```jsx
import React from 'react'

class X extends React.Component {

    state = {
        name:"Kapil"
    }

    setStateX = (newState) => {
        this.setState({name:newState})
    }

    render() {
        return (
        <div>
        <h4>Hi my name is { this.state.name } </h4>
        <Y setStateX={this.setStateX}/>
        </div>
        );
    }

}
class Y extends React.Component {

    render() {
        return(
            <div>
                <Z setStateX = {this.props.setStateX}/>
            </div>
        );
    }
}
class Z extends React.Component {
    render() {
        return(
            <div>
                <button onClick = { ()=> {
                    this.props.setStateX("Nikhil")
                }}>click to change state</button>
            </div>
        )
    }
}
export default X;
```

**输出:**

![](img/26c6a57bd0e7f50ecd38233de15ed585.png)