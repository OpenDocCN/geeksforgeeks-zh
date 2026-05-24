# Angular 与 AngularJS 之间的差异

> 原文: [https://www.geeksforgeeks.org/difference-between-angular-and-angularjs/](https://www.geeksforgeeks.org/difference-between-angular-and-angularjs/)

在本文中，我们将了解 `AngularJS` 和 `Angular`，以及它们之间的显著区别。

## AngularJS

[AngularJS](https://www.geeksforgeeks.org/introduction-to-angularjs/) 是一个 `Javascript` 开源前端框架，主要用于开发单页 web 应用程序(`SPAs`)。它是一个不断增长和扩展的框架，为开发 web 应用程序提供了更好的方法。它把静态的 `HTML` 变成了动态的 `HTML`。它的动态绑定和依赖注入等特性消除了我们编写代码的需要。`AngularJS` 发展迅速，正因为如此，我们才有了不同版本的 `AngularJS`，最新的稳定版本是 `1.7.7`。还需要注意的是，`Angular` 不同于 `AngularJS`。这是一个开源项目，任何人都可以自由使用和更改。它用指令扩展 `HTML` 属性，数据用 `HTML` 绑定。

## Angular

[Angular](https://www.geeksforgeeks.org/angular-8-introduction/) 是谷歌为开发 web 应用而创建的一个流行的开源 `Typescript` 框架。前端开发人员使用像 `Angular` 或 `React` 这样的框架来高效地呈现和操作数据。与旧版本的 `Angular` 相比，更新后的 `Angular` 效率更高，尤其是核心功能被转移到了不同的模块。这就是为什么它变得如此快速和平稳相比，旧的。新增 `angular CLI`，借助这个命令行界面，我们可以安装所需的便于创建的包，将复杂结构的代码做成易于管理的模块化形式。

尽管如此，`AngularJS` 和 `Angular` 还是有显著的关键区别，可以按照以下方式进行分类:

| Category | AngularJS | Angular |
| --- | --- | --- |
| **Architecture** | 支持[模型-视图-控制器设计](https://www.geeksforgeeks.org/model-view-controllermvc-architecture-for-node-applications/)。视图处理模型中可用的信息以生成输出。它使用组件和指令。组件是带有模板的指令。 | 它使用组件和指令。组件是带有模板的指令。 |
| **Written Language** | 用 `JavaScript` 写的。 | 用微软的 `TypeScript` 语言编写，这是 [ECMAScript 6 (ES6)](https://www.geeksforgeeks.org/introduction-to-es6/) 的超集。 |
| **Mobile Support** | 它不支持移动浏览器。 | 所有流行的移动浏览器都支持 `Angular`。 |
| **Expression Syntax** | [`ng-bind`](https://www.geeksforgeeks.org/angularjs-ng-bind-directive/) 用于将数据从视图绑定到模型，反之亦然。 | 包含在“()”和“[]”中的属性用于在视图和模型之间绑定数据。 |
| **Dependency Injection** | 它不使用依赖注入。 | 它使用依赖注入。 |
| **Routing** | `AngularJS` 使用`$routeProvider.when()`进行路由配置。 | `Angular` 使用`@RouteConfig{(…)}`进行路由配置。 |
| **Structure** | 与 `Angular` 相比，它更难管理。 | `It has a better structure compared to AngularJS, easier to create and maintain large applications but behind in AngularJS in the case of small applications.` |

**注意:** `Angular` 是一个很棒的框架，它在 `AngularJS` 方面有很多改进，它擅长更大的应用程序，也擅长更小的应用程序，但是 `Angular` 和 `AngularJS` 之间存在巨大的竞争。