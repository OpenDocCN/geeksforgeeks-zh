# 反应堆纯部件

> 原文:[https://www.geeksforgeeks.org/reactjs-pure-components/](https://www.geeksforgeeks.org/reactjs-pure-components/)

一般来说，在 [**ReactJS**](https://www.geeksforgeeks.org/react-js-introduction-working/) 中，我们使用**should component update()**life cycle 方法自定义默认行为，并在 React 组件应该重新渲染或更新自身时实现。

**先决条件:**

*   [**反应堆组件**](https://www.geeksforgeeks.org/reactjs-components/)
*   [**反应堆组件–第二组**](https://www.geeksforgeeks.org/reactjs-components-set-2/)

现在， **ReactJS** 为我们提供了一个**纯组件**。如果我们用**纯组件**扩展一个类，就不需要 **shouldComponentUpdate()** 生命周期方法。 **ReactJS 纯组件**类将当前状态和道具与新道具和状态进行比较，以决定 React 组件是应该重新渲染自己还是不应该。

简单来说，如果状态或道具的前一个值和状态或道具的新值相同，组件就不会重新渲染自己。由于**纯组件**在不使用组件的重渲染时限制重渲染。纯组件是扩展**反应的类组件。PureComponent** 。

**示例**:演示纯组件创建的程序。

## java 描述语言

```jsx
import React from ‘react’;

export default class Test extends React.PureComponent{
   render(){
      return <h1>Welcome to GeeksforGeeks</h1>;
   }
}
```

**输出**:

[![](img/2b1227d3c84b365cc120b6921a961bcc.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200717103720/Screenshotfrom20200501143518-300x86.png)

用**纯组件**扩展 React 类组件确保了组件的更高性能，并最终使您的应用程序更快，而在常规组件的情况下，它将总是重新呈现状态和道具的值是否改变。

在使用纯组件时，需要注意的是，在这些组件中，状态和道具的值是**浅比较**(浅比较)，它还处理了**应该组件更新**生命周期方法**隐含的**。
所以如果这些状态和道具对象包含嵌套数据结构，那么**纯组件的**实现的 **shouldComponentUpdate** 将返回 false，不会更新这个**类组件的**子**的整个子树。**所以在**纯组件**、中，嵌套的数据结构无法正常工作。

在这种情况下，状态和道具对象应该是简单的对象，子元素也应该是纯的，这意味着在任何实例中为相同的输入值返回相同的输出。