# ReactJS |状态 vs 道具

> 原文:[https://www.geeksforgeeks.org/reactjs-state-vs-props/](https://www.geeksforgeeks.org/reactjs-state-vs-props/)

我们知道，在 react 中，组件是可以在构建用户界面时反复使用的构建块。在进入状态和道具的主要区别之前，我们先来看看 react 中的一个组件是如何与 javascript 中的一个正常函数相关联的
**示例:**

## java 描述语言

```jsx
// simple component
class FakeComponent extends React.component{
 render(){
    return <div>Hello World!</div>
    }
}
// simple javascript function
const FakeFunction = () => console.log('Hello World!');
```

在上面的代码中，我们通过扩展 **React.component** 本地方法来声明一个简单的 react 组件，然后我们简单地呈现一个 div，其中包含“Hello World”作为文本。在函数之后，我们有一个简单的 javascript 函数在里面，它包含一个简单的控制台。log 在里面做同样的事情，打印“Hello World！”。
现在我们知道 React 组件的工作方式类似于普通的 javascript 函数。我们来看看**状态**T5

### 状态

状态是存在于组件内部的变量，不能在组件外部访问和修改，只能在组件内部使用。工作原理与在函数内部声明的变量非常相似，在普通 javascript 中，不能在函数范围之外访问该变量。状态**可以用这个. setState 修改，状态可以异步**。每当使用 this.setState 来更改状态时，State 类本身就会重新显示。让我们借助一个例子来看看:
**例子:**

## java 描述语言

```jsx
// component
class FakeComponent extends React.component{
  state = {
      name : 'Mukul';
   }
  render(){
      return <div>Hello {this.state.name}</div>
   }
}
// simple js function
const FakeFunction = () => {
  let name = 'Mukul';
  console.log(`Hey ${name}`);
}
```