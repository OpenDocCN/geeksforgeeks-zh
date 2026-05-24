# 如何在 ReactJS 中从子组件设置父状态？

> 原文:[https://www . geeksforgeeks . org/如何从子组件设置父状态-in-reactjs/](https://www.geeksforgeeks.org/how-to-set-parent-state-from-children-component-in-reactjs/)

我们可以使用以下方法从 ReactJs 中的子组件设置父状态。

**先决条件:**[ReactJS 中的状态介绍](https://www.geeksforgeeks.org/reactjs-state-react/)

*   我们实际上将在父组件本身中设置父组件的状态，但是子组件将负责设置。
*   我们将在 parent 中创建一个函数，用给定的输入设置状态。
*   我们将把这个函数作为一个道具传递给孩子们。
*   然后，子对象将使用新值调用该函数。
*   我们将在函数中设置父级的状态。

**创建反应应用程序:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹，即文件夹名称后，使用以下命令移动到该文件夹:

```jsx
cd foldername
```

**项目结构:**如下图。

![](img/9a274640a8178f2c3c9a250f84ee267a.png)

项目结构

**步骤 3:** 现在在 **src** 文件夹中创建父组件和子组件，代码如下。

**文件名- Child.js:**

## java 描述语言

```jsx
import React,{ Component }  from 'react';

class Child extends Component {

  constructor(props) {
    super(props);
    this.handleClick.bind(this);
  }

  handleClick = () => {
    // We will start the process of changing
    // state of parent from Here...
  }

  render() {
    return (
        <button onClick={this.handleClick}>Reveal Title</button>
    );
  }
}

export default Child;
```

**文件名- Parent.js:**

## java 描述语言

```jsx
import React,{ Component }  from 'react';
import "./parent_css.css"

// Importing child component for rendering
import Child from './child';

class Parent extends Component {

  constructor(props) {
    super(props);
    this.state = {title: ""};
  }

  render() {
    return (
        <React.Fragment>
          // Rendering title of state initially empty.
          <h1> {this.state.title} </h1>

          // Rendering child component here which 
          // contains only a button
          <Child />
        </React.Fragment>
    );
  }
}

export default Parent;
```

**第四步:**创建函数*设置父组件中父组件的状态*，同时在子组件中传递*设置父组件的状态*函数。

**文件名- Parent.js:**

## java 描述语言

```jsx
import React,{ Component }  from 'react';
import "./parent_css.css"

import Child from './child';

class Parent extends Component {

  constructor(props) {
    super(props);
    this.setStateOfParent.bind(this);
    this.state = {title: ""};
  }

  // Creating below function to set state 
  // of this (parent) component.
  setStateOfParent = (newTitle) => {
    this.setState({title: newTitle});
  }

  render() {
    return (
        <React.Fragment>
          <h1> {this.state.title} </h1>

          // Passing the setStateOfParent function 
          // in child as a prop
          <Child setStateOfParent = {this.setStateOfParent}/>
        </React.Fragment>
    );
  }
}

export default Parent;
```

**第 5 步:**现在，只要您想设置父项的状态，就可以访问并调用子项中的*设置父项的状态*功能。

**文件名- Child.js:**

## java 描述语言

```jsx
import React,{ Component }  from 'react';

class Child extends Component {

  constructor(props) {
    super(props);
    this.handleClick.bind(this);
  }

  handleClick = () => {
    // Simply call the setStateOfParent function from 
    // prop and pass required argument
    this.props.setStateOfParent("Geeks For Geeks");
  }

  render() {
    return (
        <button onClick={this.handleClick}>Reveal Title</button>
    );
  }
}

export default Child;
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/90b406cdc4b220f8c0ff83c0d660fb89.png)