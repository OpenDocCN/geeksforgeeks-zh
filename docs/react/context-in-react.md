# 反应中的上下文

> 原文:[https://www.geeksforgeeks.org/context-in-react/](https://www.geeksforgeeks.org/context-in-react/)

在本文中，将向您介绍 React Context，它是 React 应用程序中的最新功能之一。
先决条件:ReactJS-基础、类型脚本(带接口)、ES6 符号

**什么是反应语境？**
React Context 是一种将道具从父组件传递给子组件的方法，方法是将道具存储在商店中(类似于 Redux)，并由子组件使用商店中的这些道具，而无需在组件树的每个级别手动传递它们。

**为什么反应语境？我们有 Redux！！**
使用 Redux 与从父组件到子组件的状态进行交互不仅很难理解，还会给你一个更复杂的代码。通过上下文的使用，概念和代码的理解远比 Redux 容易。

**什么时候使用 React Context？**
任何时候都可以！没有一成不变的规则，比如什么时候在应用程序中使用上下文。无论何时，如果您希望存储区保存您的状态或变量，并在程序的其他地方使用它们，请使用上下文。一般来说，当我们的组件树中有两个或两个以上的级别(高度)时，使用存储代替传递道具然后提升状态是可行的，因为这会造成混乱和不必要的冗长代码。
<u>示例:</u>
如果我们的 app 中有三个组件，A- > B- > C 其中 A 是 B and B 的父项，C 是 C 的父项，要将一个状态从 C 更改并传递给 A，将 A 的状态保留在一个商店中，然后从商店中提取该状态并在 C 中使用，这就完全消除了状态通过 B 的必要性，所以流程就像 A- > C 一样

**用法**
现在我们用一个简单的例子来理解。
首先，我们定义一个由学生姓名和标记组成的界面(或类):

> 界面标记文本{
> 名称:字符串；
> 标志:数字；
> }

现在在上下文中定义这个接口。

> const context marks = react . create context(null)；
> //用空值初始化的标记文本接口属性定义的上下文

创建提供商和消费者

> const MarksContextProvider = context marks。提供者；
> //这是状态将作为道具保存和传递的商店。
> const MarksContextConsumer = context marks。消费者；
> //这是存储在提供者
> //上下文中的状态将由子组件提取并根据用户使用的存储。

现在，让我们的组件树结构像 A->B->C(从上面看)。我们将在字典中存储一些名称和标记的值，传递来自 A 的信息以在 C 中显示它，而不干涉 b。

完整代码:

**注意:**将两个文件保存在同一个目录下。
1。MarksContext.tsx(类型脚本)

## java 描述语言

```jsx
import * as React from "react";

export interface MarksContext{
  name: string;
  marks: number;
}
const contextmarks = React.createContext<MarksContext | null>(null);
export const MarksContextProvider = contextmarks.Provider;
export const MarksContextConsumer = contextmarks.Consumer;
```

2.App.tsx(类型脚本)

## java 描述语言

```jsx
import * as React from "react";
import { render } from "react-dom";
import { MarksContext, MarksContextProvider } from "./MarksContext";
import {  MarksContextConsumer } from "./MarksContext";

const sample: MarksContext = {
  name: "X",
  marks: 20

};

export const A = () => (
  <MarksContextProvider value={sample}>
    <B />
  </MarksContextProvider>
);

const B = () => (
  <div>
    <h2>Student Info</h2>
    <C />
  </div>
);

const C = () => (
  <MarksContextConsumer>
    {appContext =>
      appContext && (
        <div>
          Name: {appContext.name} <br />
          Marks: {appContext.marks} <br />
        </div>
      )
    }
  </MarksContextConsumer>
);

render(<A />, document.getElementById("root"));
```

**输出:**

![](img/ee8b848de1040630706f2879b3f5004d.png)

**<u>工作:</u>**
首先在界面*标记中声明信息，然后在*上下文标记*中定义界面信息。提供者(*标记文本提供者*)和消费者(*标记文本消费者*)在此上下文中定义。
*MarksContextProvider*放在 *A* 中，我们的应用程序的根，其*值*按照*示例*中给出的初始化。随后将 *MarksContextConsumer* 放入 C 中，通过 *appContext* 提取接口的值，作为 *MarksContext* 接口的实例。最后，该值用 c 显示*

**注意:**只有提供者内提到的组件( *MarksContextProvider* )及其子组件才能使用 Consumer(*MarksContextConsumer*)修改状态。