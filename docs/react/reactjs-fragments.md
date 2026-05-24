# 反应堆碎片

> 原文:[https://www.geeksforgeeks.org/reactjs-fragments/](https://www.geeksforgeeks.org/reactjs-fragments/)

我们知道，每当我们想要在屏幕上呈现一些东西时，我们都会在组件内部使用 render 方法。我们可以渲染单个元素或多个元素，但是渲染多个元素需要在内容周围有一个**【div】**标记，因为渲染方法一次只能渲染其中的一个根节点。

**示例:**创建一个 React 应用程序，并从 src 文件夹中编辑 **App.js** 文件，如下所示:

**文件名- App.js:**

## java 描述语言

```jsx
import React from "react";

// Simple rendering with div
class App extends React.Component {
  render() {
    return (
      // Extraneous div element
      <div>
        <h2>Hello</h2>

        <p>How you doin'?</p>
      </div>
    );
  }
}

export default App;
```

**输出:**

![](img/ac2b30a77a907ed49b39c6a842bae437.png)

**使用 Fragments 的原因:**正如我们在上面的代码中看到的，当我们试图渲染多个根元素时，我们必须将整个内容放在‘div’标签中，这并不被许多开发人员所喜欢。所以在 React 16.2 版本中，引入了**片段**，我们用它们来代替无关的‘div’标签。

**语法:**

```jsx
<React.Fragment>  
      <h2>Child-1</h2>   
      <p> Child-2</p>   
</React.Fragment>  
```

**示例:**打开 **App.js** 并用下面的代码替换代码。

## java 描述语言

```jsx
import React from "react";

// Simple rendering with fragment syntax
class App extends React.Component {
  render() {
    return (
      <React.Fragment>
        <h2>Hello</h2>

        <p>How you doin'?</p>
      </React.Fragment>
    );
  }
}

export default App;
```

**输出:**

![](img/ac2b30a77a907ed49b39c6a842bae437.png)

**速记片段:**第一个代码的输出和上面的代码是一样的，但是使用的主要原因是，与内部带有‘div’标签的代码相比，它要快一点，因为我们没有创建任何 DOM 节点。此外，它需要较少的内存。上述方法还有另一种简写，即我们用“< >”和“< / >”代替“反应”。碎片。

**注意:**简写语法不接受键属性，在这种情况下你必须使用< React。碎片>标记。
**语法:**

```jsx
<>  
      <h2>Child-1</h2>   
      <p> Child-2</p>   
</> 
```

**示例:**打开 **App.js** 并用下面的代码替换代码。

## java 描述语言

```jsx
import React from "react";

// Simple rendering with short syntax
class App extends React.Component {
  render() {
    return (
      <>
        <h2>Hello</h2>

        <p>How you doin'?</p>
      </>
    );
  }
}

export default App;
```

**输出:**

![](img/ac2b30a77a907ed49b39c6a842bae437.png)