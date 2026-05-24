# 什么是 React 中的 StrictMode？

> 原文:[https://www.geeksforgeeks.org/what-is-strictmode-in-react/](https://www.geeksforgeeks.org/what-is-strictmode-in-react/)

StrictMode 是一个 React Developer Tool，主要用于突出显示 web 应用程序中可能出现的问题。它为其子组件激活额外的折旧检查和警告。它受欢迎的原因之一是，每当没有遵循 React 指导方针和推荐做法时，它都会提供视觉反馈(警告/错误消息)。就像反应片段一样，反应严格模式组件不呈现任何可见的用户界面。

React StrictMode 可以被视为一个帮助组件，它允许开发人员高效地编写代码，并提醒他们注意任何可能意外添加到应用程序中的可疑代码。StrictMode 可以应用于应用程序的任何部分，不一定适用于整个应用程序。在开发新代码或调试应用程序时使用它特别有帮助。

**例:**

## Javascript

```jsx
import React from 'react';

function StictModeDemo() {
  return (
    <div>
      <Component1 />
      <React.StrictMode>
        <React.Fragment>
          <Component2 />
          <Component3 />
        </React.Fragment>
      </React.StrictMode>
      <Component4 />
    </div>
  );
}
```

**解释:**在上面的例子中，严格模式检查将只适用于组件 2 和组件 3(因为它们是 React 的子组件。StrictMode)。与此相反，组件 1 和组件 4 将不进行任何检查。

**优势:**React strict mode 有助于识别和检测开发阶段的各种警告/错误，即-

1.  **Helps identify those components with unsafe life cycle:** Some legacy component life cycle methods are considered unsafe to use in asynchronous applications. The strict response mode is helpful to detect the use of this unsafe method. When enabled, it displays a list of all components that use unsafe life cycle methods as warning messages.
2.  **Warning the use of legacy string reference API:** At first, there were two ways to manage references-legacy string reference API and callback API. Later, a third alternative method, createRef API, was added to replace string references with object references, which allowed StrictMode to give warning messages when using string references.
3.  **Warning usage of findDOMNode that is not recommended:** Because findDOMNode is only a one-time read API, when a child component tries to present different nodes (except the nodes presented by the parent component), it cannot handle the changes. These problems are detected by the reaction strict mode and displayed as warning messages.

**需要记住的附加要点:**

*   Since StrictMode is a developer tool, it only runs in development mode. It will not affect the production build in any way.
*   In order to identify and detect any problems in the application and display warning messages, StrictMode renders each component in the application twice.