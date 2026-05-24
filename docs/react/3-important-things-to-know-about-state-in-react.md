# 反应状态需要了解的 3 件重要事情

> 原文:[https://www . geeksforgeeks . org/3-重要的事情-了解处于反应中的状态/](https://www.geeksforgeeks.org/3-important-things-to-know-about-state-in-react/)

**React**……我们都知道这个框架在开发者或者程序员中的受欢迎程度。React 坐在所有流行的 JavaScript 库的顶端。理解 React 的概念及其不同的细分市场非常重要。

![3-Important-Things-to-Know-About-State-in-React](img/04188885bc70bd79eee330653325a794.png)

状态哪个是**的心脏[反应过来](https://www.geeksforgeeks.org/reactjs-tutorials/)** 是最要学习的概念。它的行为，它的变化以及它在组件不同部分的工作方式。作为一个反应开发者，你应该知道如何正确使用它。在构建应用程序时，您必须避免一些常见的陷阱。

在这篇文章中，我们将讨论国家最重要的五个部分。这些部分是建立在彼此之上的，以使您理解“反应”中的复杂主题。为了使概念清晰，我们将讨论许多你可以自己检查的实际例子。

### **1。使用状态更新无法合并状态。**

当一个 React 开发人员使用 [React 钩子](https://www.geeksforgeeks.org/introduction-to-react-hooks/)从基于类的组件移动到基于函数的组件时，状态更新不再自动合并。

您可以根据需要多次调用 useState 钩子来使用任意多的变量。在下面给出的例子中…我们有一个带有电子邮件和密码输入的基本表单。我们将把它们中每一个的状态作为单独的状态变量来管理。

## java 描述语言

```jsx
import React from "react";

export default function App() {
  const [email, setEmail] = React.useState("");
  const [password, setPassword] = React.useState("");

  return (
    <form>
      <input
        name="email"
        type="email"
        placeholder="Email"
        onChange={(e) => setEmail(e.target.value)}
      />
      <input
        name="password"
        type="password"
        placeholder="Password"
        onChange={(e) => setPassword(e.target.value)}
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

现在让我们对上面的例子做一些修改。我们可以在单个对象中管理表单状态。这将允许您只调用一次 useState。电子邮件和密码不会由单个状态变量管理。

现在的问题是……当它是一个对象时，我们如何用 setState 函数更新状态？

在表单输入中，我们可以添加 onChange prop。这个 onChange 道具将由通用事件处理程序处理。看看下面给出的代码快照…

## java 描述语言

```jsx
import React from "react";

export default function App() {
  const [state, setState] = React.useState({
    email: '',
    password: ''
  })

  function handleInputChange(e) {
    setState({
      [e.target.name]: e.target.value
    })
  }

  return (
    <form>
      <input
        name="email"
        type="email"
        onChange={handleInputChange}
      />
      <input
        name="password"
        type="password"
        onChange={handleInputChange}
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

在上面的例子中，状态根据用户当前输入的名称进行更新。这种模式基本上用在基于类的组件中，但它不适用于 useState 钩子。当你用 useState 的 setState 函数更新状态时，它不会自动合并。

**具体是什么意思…？**

这仅仅意味着，每当我们将状态设置为用户键入时，先前的状态不会被包括在内。现在，有什么解决办法或选择包括州？？

我们可以通过使用 spread 操作符手动完成。

## java 描述语言

```jsx
import React from "react";

export default function App() {
  const [state, setState] = React.useState({
    email: '',
    password: ''
  })

  function handleInputChange(e) {
    setState({
      // spread in previous state with object spread operator
      ...state,
      [e.target.name]: e.target.value
    })
  }

  return (
    <form>
      <input
        name="email"
        type="email"
        onChange={handleInputChange}
      />
      <input
        name="password"
        type="password"
        onChange={handleInputChange}
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

### **2。状态更新应该是不可变的**

应以正确的方式管理和更新反应状态。要使用 useState 钩子管理状态，您应该只使用专用的 setter 函数，该函数是作为数组中的第二个元素提供的，您从 useState 返回来更新它。如果您不这样做，并且您将尝试使用普通的 JavaScript 示例手动更新它，那么您将无法从应用程序中找到预期的行为。

请记住，状态更新正确，导致我们的组件重新渲染。现在有一个问题……如果我们用自己的方式而不是“反应”的方式更新状态，它会发生什么。在这种情况下，当某些事情发生变化时，React 将负责显示和呈现组件。

关键是……如果你用普通的 JavaScript 而不是 setState 来更新状态，那么它不会触发重新渲染，React 也不会向用户显示状态的变化。

在反应中，重要的是要知道，如何使用反应来更新状态，哪一个是合适的状态挂钩来实现您的目的。您可以选择 useReducer、useState 或像 Redux 这样的第三方状态管理库。你不能直接更新或改变你的状态。

状态更新应该总是不可变的。直接改变您的状态会使您的状态不可预测，并且会在您的应用程序中导致意想不到的问题。

## java 描述语言

```jsx
import React from 'react';

export default function App() {
  const [count, setCount] = React.useState(0);

  // Don't assign state to new (non-state) 
  // variables. Below code is not acceptable.
  const newCount = count;

  // Don't directly mutate state
  const countPlusOne = count + 1;

  return (
    <>
      <h1>Count: {count}</h1>
    </>
  );
}
```

### 3.**状态更新是异步和预定的，不能立即执行**

另一个需要考虑的重要概念是，状态更新不会立即执行。如果你看一下 React 文档，你会发现当你调用 setState 函数时会发生什么。您可以使用它来更新与之关联的状态变量。您可以查看 React 文档，看看调用 setState 函数时会发生什么。

您可以使用它来更新与之关联的状态变量。我们被告知它接受一个新的状态值，并对组件进行重新渲染。这是什么意思？？

这意味着组件不会立即重新呈现。这通常是出于性能的目的，它让我们更好地了解 React 在幕后做什么。

setState 函数不会立即更新状态，它只是计划在未来的某个时间更新状态。查看代码并准确地看到状态更新发生或将要发生的时间并不容易。

这有利于比较 useRef，考虑到它目前的属性，我们之前提到过它能够保留数据。使用 useRef 进行的更新是同步执行的。查看代码，查看更新何时在 useRef 中执行，而不是在 useState 中执行。

### 结论

正如我们已经讨论过的，状态是反应的核心。当您在 React 上工作时，您需要在编写代码时小心。状态行为非常重要，理解你在 React 应用程序中如何处理状态很重要。本文的第二点很重要，要理解。一旦你开始工作，随着你的进步，你会发现自己在项目中做得更好。理解状态行为最好的方法是破解代码，看看事情是如何运作的。