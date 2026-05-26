# 反应堆组件完整参考

> 原文：[https://www.geeksforgeeks.org/reactjs-components-complete-reference/](https://www.geeksforgeeks.org/reactjs-components-complete-reference/)

`组件`是自由和可重用的代码。它们的作用类似于 `JavaScript` 函数。但是，工作隔离并通过呈现函数返回 `HTML`。

一个`组件`是 `React` 的核心构件之一。换句话说，我们可以说，您将在 `React` 中开发的每个应用程序都将由称为组件的部分组成。组件使得构建用户界面的任务变得更加容易。您可以看到一个用户界面被分解成多个独立的部分，称为组件，并独立地处理它们，将它们全部合并到一个父组件中，这将是您的最终用户界面。

`React` 中的组件基本上返回一段 `JSX` 代码，它告诉应该在屏幕上呈现什么。在 `React` 中，我们主要有两类组件：

*   `Functional component`：一个`Functional component`就是一个 `JavaScript` 函数。我们可以编写一个 `JavaScript` 函数来创建一个 `React` 函数组件。这些函数可以接受数据作为参数，也可以不接受，我们将在本教程的后面讨论这一点。以下示例展示了一个有效的 `React` 函数组件：

## Javascript

```jsx
function Democomponent()
{
    return <h1>Welcome Message!</h1>;
}
```