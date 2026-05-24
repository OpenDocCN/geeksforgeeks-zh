# 如何在 ReactJS 中创建组件？

> 原文:[https://www . geesforgeks . org/how-to-create-components in-reactjs/](https://www.geeksforgeeks.org/how-to-create-components-in-reactjs/)

众所周知，React 使用这种 JSX 格式，因此我们可以将 HTML 和 JavaScript 放在一起。这些反应组件可以在您的反应项目中的任何地方定义，也可以在您的反应项目中的任何地方使用。在 ReactJS 中定义组件有两种方法，两种方法都被广泛的程序员使用，但是随着像 useState、use context 这样的 API/HOOKs 的出现，功能组件变得越来越流行。

### 组件类型:

1.  反应功能组件
2.  反应基于类的组件

**1。反应功能组件:**反应功能组件可以是任何返回 HTML 的 JavaScript 函数。这些功能组件也可以接受“道具”，即属性或数据。由于这些是 JavaScript 函数或 JavaScript 函数的扩展，它们也可以从箭头函数的 ES6 约定中创建。这些功能组件还可以接受我们可以使用 JSX 语法的道具，并且您还可以将正常的 JavaScript 代码放在 return 语句之前。需要注意的一点是，每个组件应该只有一个退货。

**语法:**

## Javascript

```jsx
const Greet = (props) => {
    const person = props.name;
  return (
    <div>
      <h1>Hello {person}!!</h1>
    </div>
  )
}
```