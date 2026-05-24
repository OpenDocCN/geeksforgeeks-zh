# AngularJS vs Angular2 |特性和比较

> 原文:[https://www . geeksforgeeks . org/angular js-vs-angular 2-特征和比较/](https://www.geeksforgeeks.org/angularjs-vs-angular2-features-and-comparison/)

**[AngularJS:](https://www.geeksforgeeks.org/introduction-to-angularjs/)** 是一个前端动态 JavaScript 框架，用于开发‘单页应用’。AngularJS 由谷歌管理，是开源的。这意味着它对全球的开发者开放。正因为如此，网上有很多资料可以免费获取，来学习这项技术。推出后，AngularJS 迅速走红。这是因为它向开发人员提供了大量功能，如数据绑定、更简单的事件处理等。

**Angular 2:** 建立在‘Typescript’上。Typescript 是一种开源编程语言，由微软管理。Angular 2 与 AngularJS 完全不同。AngularJS 具有诸如控制器、$scope、$scope 变量等特性。然而，在 Angular 2 中，这些特性被新特性(即组件和指令)所取代。

**AngularJS 特性:**

*   **MVC 框架:**AngularJS 的‘模型视图控制’架构本质上是动态的。“模型”涵盖了应用程序的数据和逻辑部分，“视图”涵盖了应用程序的美学，而“控制器”将这两者联系起来，并使应用程序作为一个整体一起运行。因此，所有组件都是单独构建的，然后在以后组合在一起。
*   **用户界面:** AngularJS 使用基本的 HTML 标签创建用户界面。
*   **少代码，多做事:**使用 AngularJS 的最大优势在于，与 jQuery 等其他库相比，使用 AngularJS 创建相同功能所需的代码行更少。数据绑定是这背后的主要因素。
*   **过滤器:**它有助于创建分页系统，并根据给定的参数过滤数据数组。例如，假设有一个数据数组包含所有小于 5 的自然数，即[1，2，3，4，5]。
    现在假设应用了一个过滤器，只允许小于 4 的数字添加到结果数组中。因此，结果数组将是[1，2，3]。这可以通过使用 AngularJS 过滤器来实现。
*   **表达式:**AngularJS 表达式写在两个大括号内。{{expression}}。这些在双向数据绑定中很有用。
*   **双向数据绑定:**这有助于在模型和视图之间创建同步。模型中所做的更改会立即反映在视图中，视图中的更改也会立即反映在模型中。这在创建 SPa 时非常有用。

**角度 2 特征:**

*   **移动开发:** Angular 2 有助于开发响应性的移动应用。
*   **性能:**应用的加载时间减少。动态加载功能有助于减少加载时间。
*   **路由:**位置服务和导航模型等功能改进了 Angular 2 中的路由服务。
*   **跨平台:** Angular 2 应用可以在安卓、iOS、Windows 等所有设备和平台上运行。
*   **浏览器支持:** Angular 2 几乎支持谷歌 Chrome、Safari、Edge 等所有现代浏览器。

**AngularJS 与 Angular 2 的比较:**Angular js 与 Angular 2 的比较。

| **因子** | **角 JS** | **角度 2** |
| **语言** | 用 JavaScript 写的。 | 用 TypeScript(Javascript 的超集)编写。 |
| **布线** | $routeprovider.when()用于路由配置。 | @RouteConfig{}用于路由。 |
| **架构** | 使用 MVC 架构来构建应用程序。 | 使用 MVVM 架构构建应用程序。 |
| **移动支持** | AngularJS 不支持手机。 | Angular 2 是专门为移动用户开发的。 |
| **并发症** | 学习起来更容易。但是，一旦一次用户数量超过 200，应用程序就会开始滞后。 | 这对于创建小应用程序来说是低效的，因为设置 Angular 2 开发环境是困难的。 |
| **语法** | 句法学起来很复杂。 | 语法比 AngularJS 相对容易。 |
| 插件 | 开发不需要额外的插件。 | Angular 2 需要额外的插件进行开发。 |