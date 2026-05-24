# 反应中的代码拆分

> 原文:[https://www.geeksforgeeks.org/code-splitting-in-react/](https://www.geeksforgeeks.org/code-splitting-in-react/)

代码拆分是像 Webpack、Rollup 和 Browserify 这样的捆绑包支持的功能，它可以创建多个可以在运行时动态加载的捆绑包。
随着网站越来越大，越来越深入组件，它变得越来越重。当包含来自第三方的库时尤其如此。代码拆分是一种有助于生成能够动态运行的包的方法。这也有助于提高代码的效率，因为该包包含所有必需的导入和文件。
**捆绑及其效率:**捆绑是将导入的文件合并成单个文件的方法。这是在**网络包、汇总、浏览**的帮助下完成的，因为他们可以创建许多可以在运行时动态加载的包。
借助代码拆分，可以实现‘懒加载’，也就是说只使用当前需要的代码。

*   默认导入方式如下:

## java 描述语言

```jsx
import { add } from './math';
console.log(add(x, y));

// Here x, y are two numbers
```

*   使用代码拆分，可以按如下方式完成:

## java 描述语言

```jsx
import("./math").then(math => {
  console.log(math.add(x, y));
});

// Here x, y are two numbers
```

一旦 Webpack 获得这种类型的语法，代码拆分就会自动开始。使用创建反应应用程序时，它已经设置好，可以立即使用。
如果使用 Webpack，应遵循关于代码拆分的 Webpack 指南。这些指令可以在 https://webpack.js.org/guides/code-splitting/.
中找到当使用巴别塔时，必须确保巴别塔没有转换导入语法，而是可以动态解析它。这可以使用 https://classic . yarn pkg . com/en/package/babel-plugin-语法-dynamic-import package 来完成。
**React.lazy 和 suspension:**由于 React.lazy 和 suspension 现在还不能在服务器上渲染，建议在服务器渲染的应用中使用 https://github.com/gregberge/loadable-components 进行代码拆分。React.lazy 有助于将动态导入作为常规组件呈现。
**之前:**

```jsx
import Component from './Component';
```

**之后:**

```jsx
const Component = React.lazy(() => import('./Component'));
```

当第一次呈现该组件时，包将被单独加载，其中包含该组件。
惰性组件应该在悬疑组件中呈现，这有助于在惰性组件加载时反映一些后备内容。

## java 描述语言

```jsx
import React, { Suspense } from 'react';
const Component = React.lazy(() => import('./Component'));
function MyComponent() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
    </div>);
}
```

回退道具可以接受任何将在等待组件加载时呈现的 React 元素。悬疑组件可以放在惰性组件上方的任何位置。此外，多个惰性组件可以用单个暂挂组件包装。

## java 描述语言

```jsx
import React, { Suspense } from 'react';

const ComponentOne =
 React.lazy(() => import('./ComponentOne'));
const ComponentTwo =
 React.lazy(() => import('./ComponentTwo'));
function MyComponent() {
  return (
<div><Suspense fallback={<div>Loading...</div>}></div>);
}
```

**错误边界:**当某些模块由于任何问题而无法加载时，将触发错误。通过使用合适的错误页面，可以正确处理这些错误，并为用户提供良好的体验。

## java 描述语言

```jsx
import React, { Suspense } from 'react';
import ErrorBoundary from './ErrorBoundary';
const ComponentOne = React.lazy(() =>
 import('./ComponentOne'));
const ComponentTwo = React.lazy(() =>
 import('./ComponentTwo'));
const MyComponent = () => (
  <div>
    <Suspense fallback={<div>Loading...</div>}>
  </div>
);
```

**基于路由的代码拆分:**代码中可能很难实现代码拆分，可以将捆绑包平均拆分，这样会为用户提升体验。
T3】例:

## java 描述语言

```jsx
import React from 'react';
import Suspense from 'react';
import lazy from 'react';
import {Route, Switch, BrowserRouter }
            from 'react-router-dom';

const HomePage = lazy(() =>
 import('./routes/HomePage'));
const AboutUs = lazy(() =>
 import('./routes/AboutUs'));
const App = () =>
 (<Suspense fallback={<div>Loading...</div>}>
);
```

**命名导出:** React.lazy 目前只支持默认导出。如果要导入使用命名导出的模块，必须创建一个默认情况下重新导出的中间模块。这确保了树摇动的工作，并防止拉进未使用的组件。

## java 描述语言

```jsx
// Components.js
export const Component = /* ... */;
export const MyUnusedComponent = /* ... */;

// Component.js
export { Component as default } from "./Components.js";

// MyApp.js
import {React, lazy} from 'react';
const Component = lazy(() => import("./Component.js"));
```