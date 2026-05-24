# ReactJS |巴别塔简介

> 原文:[https://www . geesforgeks . org/reactjs-introduction-to-babel/](https://www.geeksforgeeks.org/reactjs-introduction-to-babel/)

**通天塔简介**
通天塔是一个非常著名的 **transpiler** ，它基本上允许我们在今天的浏览器中使用未来的 JavaScript。简单来说，它可以将最新版本的 JavaScript 代码转换成浏览器能够理解的版本。JavaScript 遵循的最新标准版本是 ES2020，它不是所有浏览器都完全支持的，因此我们使用了一个工具，比如“巴别塔”，这样我们就可以将其转换成今天浏览器能够理解的代码。

**什么是 transpiler？**
是用来将源代码转换成另一个同级别源代码的工具。这就是为什么它也被称为源到源编译器。这两个代码在本质上是等价的，考虑到一个代码适用于浏览器的特定版本，而另一个代码不适用。

**注意:**同样值得注意的是，编译器与 trans filer 完全不同，trans filer 将源代码转换为另一个相同抽象层次的源代码，而编译器一般将代码转换为较低层次的代码。像在 Java 中，源代码被转换成字节码，这是较低的级别，不等同。

**我们为什么需要巴别塔？**
我们需要 babel 的主要原因是，它给了我们特权，让我们可以利用 JavaScript 提供的最新东西，而不用担心它是否能在浏览器中工作。

**简单示例**
在安装和使用巴别塔工具的所有功能之前，让我们看一个最新标准版 ES2017 的简单代码，看看当我们将其传递到巴别塔引擎时会发生什么。

**代码:**

## java 描述语言

```jsx
// sample new version javascript code
const fun = (x) => {x*2};

const a = () => {};

const b = (x) => x;

[1, 2, 3].map((n)=> n+1);
```

上面的一些代码在某些浏览器中不受支持，所以在通读巴别塔之后，我们会得到:

## java 描述语言

```jsx
// after transpiling
"use strict";

var fun = function fun(x) {
  x * 2;
};

var a = function a() {};

var b = function b(x) {
  return x;
};

[1, 2, 3].map(function (n) {
  return n + 1;
});
```

在下一篇文章中，我们将学习如何安装巴别塔，并将看到更多的例子。