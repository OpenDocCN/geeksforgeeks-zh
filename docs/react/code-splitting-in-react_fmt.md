# React 中的代码拆分

> 原文: [https://www.geeksforgeeks.org/code-splitting-in-react/](https://www.geeksforgeeks.org/code-splitting-in-react/)

代码拆分是像 Webpack、Rollup 和 Browserify 这样的打包工具支持的一项功能，它可以创建多个可以在运行时动态加载的包。随着网站越来越大，组件层级越来越深，它也变得越来越重。当包含来自第三方的库时尤其如此。代码拆分是一种有助于生成能够按需运行的包的方法。这也有助于提高代码的效率，因为该包只包含当前必需的导入和文件。

## 打包及其效率

打包是将导入的文件合并成单个文件的方法。这是在 **Webpack**、**Rollup**、**Browserify** 的帮助下完成的，因为它们可以创建许多可以在运行时动态加载的包。借助代码拆分，可以实现“懒加载”，也就是说只使用当前需要的代码。

### 默认导入方式

```jsx
import { add } from './math';
console.log(add(x, y));

// Here x, y are two numbers
```

### 动态导入

使用代码拆分，可以按如下方式完成：

```jsx
import("./math").then(math => {
  console.log(math.add(x, y));
});

// Here x, y are two numbers
```

一旦 Webpack 获得这种类型的语法，代码拆分就会自动开始。使用 Create React App 时，它已经设置好，可以立即使用。如果使用 Webpack，应遵循关于代码拆分的 Webpack 指南。这些指令可以在 [https://webpack.js.org/guides/code-splitting/](https://webpack.js.org/guides/code-splitting/) 中找到。当使用 Babel 时，必须确保 Babel 没有转换 `import()` 语法，而是可以动态解析它。这可以使用 [babel-plugin-syntax-dynamic-import](https://classic.yarnpkg.com/en/package/babel-plugin-syntax-dynamic-import) 包来完成。

## React.lazy 和 Suspense

由于 `React.lazy` 和 Suspense 目前还不能在服务器端渲染，建议在服务器渲染的应用中使用 [loadable-components](https://github.com/gregberge/loadable-components) 进行代码拆分。`React.lazy` 有助于将动态导入作为常规组件呈现。

### 之前

```jsx
import Component from './Component';
```

### 之后

```jsx
const Component = React.lazy(() => import('./Component'));
```

当第一次渲染该组件时，包含该组件的包将被单独加载。懒组件应该在 `Suspense` 组件中呈现，这有助于在懒组件加载时显示一些后备内容。

```jsx
import React, { Suspense } from 'react';
const Component = React.lazy(() => import('./Component'));
function MyComponent() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <Component />
      </Suspense>
    </div>
  );
}
```

`fallback` 属性可以接受任何将在等待组件加载时呈现的 React 元素。`Suspense` 组件可以放在懒组件上方的任何位置。此外，多个懒组件可以用单个 `Suspense` 组件包装。

```jsx
import React, { Suspense } from 'react';

const ComponentOne = React.lazy(() => import('./ComponentOne'));
const ComponentTwo = React.lazy(() => import('./ComponentTwo'));

function MyComponent() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <ComponentOne />
        <ComponentTwo />
      </Suspense>
    </div>
  );
}
```

## 错误边界

当某些模块由于任何问题而无法加载时，将触发错误。通过使用合适的错误边界，可以正确处理这些错误，并为用户提供良好的体验。

```jsx
import React, { Suspense } from 'react';
import ErrorBoundary from './ErrorBoundary';

const ComponentOne = React.lazy(() => import('./ComponentOne'));
const ComponentTwo = React.lazy(() => import('./ComponentTwo'));

const MyComponent = () => (
  <ErrorBoundary>
    <Suspense fallback={<div>Loading...</div>}>
      <ComponentOne />
      <ComponentTwo />
    </Suspense>
  </ErrorBoundary>
);
```

## 基于路由的代码拆分

在代码中实现代码拆分可能很难，可以将打包文件平均拆分，这样会为用户提升体验。

### 示例

```jsx
import React, { Suspense, lazy } from 'react';
import { Route, Switch, BrowserRouter } from 'react-router-dom';

const HomePage = lazy(() => import('./routes/HomePage'));
const AboutUs = lazy(() => import('./routes/AboutUs'));

const App = () => (
  <BrowserRouter>
    <Suspense fallback={<div>Loading...</div>}>
      <Switch>
        <Route exact path="/" component={HomePage} />
        <Route path="/about" component={AboutUs} />
      </Switch>
    </Suspense>
  </BrowserRouter>
);
```

## 命名导出

`React.lazy` 目前只支持默认导出。如果要导入使用命名导出的模块，必须创建一个默认情况下重新导出的中间模块。这确保了树摇动（tree-shaking）正常工作，并防止拉进未使用的组件。

```jsx
// Components.js
export const Component = /* ... */;
export const MyUnusedComponent = /* ... */;

// Component.js
export { Component as default } from "./Components.js";

// MyApp.js
import React, { lazy } from 'react';
const Component = lazy(() => import("./Component.js"));
```