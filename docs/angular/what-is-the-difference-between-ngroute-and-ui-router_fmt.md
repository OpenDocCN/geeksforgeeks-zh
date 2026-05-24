# ngRoute 和 ui-router 有什么区别？

> 原文：[https://www.geeksforgeeks.org/what-is-the-difference-between-ngroute-and-ui-router/](https://www.geeksforgeeks.org/what-is-the-difference-between-ngroute-and-ui-router/)

## 介绍

`ngRoute` 是 AngularJS 团队开发的一个模块，它是 AngularJS 早期核心的一部分。这是一个模块，这样可以更好地管理基本场景，更少的复杂性处理得更好。

`ui-router` 是在 AngularJS 项目之外制作的框架，用于增强和提高路由能力。这是一个框架，因此它将帮助您组织项目界面的各个部分。

他们都有独特的能力，在他们之间的选择取决于你的项目。你必须知道哪一个对你的工作项目更有用，下面提供了两者的功能，可以让你理清思路，你应该为你的项目选择哪一个。

## 对比表格

| ngRoute | ui-router |
| --- | --- |
| `ngRoute` is ideal for smaller apps that don't need to inherit pages from other sections. | `ui-router` is effective for larger applications because it allows `nested views` and `multiple named views`, and it helps to inherit pages from other parts. |
| All the links must be changed manually in `ngRoute`, which is time-consuming for larger applications, but the smaller application `ngRoute` will execute faster. | In `ui-router`, it allows strongly typed links between states, so if you change the links anywhere, it will change the links everywhere. Must be used by `ui-sref`. |
| `ngRoute` 的路由器提供者 `$routeProvider` | `ui-router` 的路由器提供者 `$stateProvider` |
| The template view of `ngRoute` is `ng-view`, which is better than `ui-view`. | Template view of `ui-router` `ui-view` is more powerful for multi-page inheritance of other parts. |
| You can't be sure if you're in a state. | You can easily determine whether you are in the parent of adjusting the status or status of UI elements in the template through `$state` provided by `ui-router`, and you can expose the status by setting it in `$rootScope` at runtime. |
| `ngRoute` 的路由器启动事件 `$routeChangeStart` | `ui-router` 的路由器启动事件 `$stateChangeStart` |
| 要在 `ngRoute` `$route -> $route.current.params.id` | `Ui-router` organized around state routing. |

## 结论

两者对于各自的领域表现都比较好，在两者之间选择取决于你的项目。如果您的项目应用程序包含复杂的视图，我会更喜欢 `ui-router` 而不是 `ng-Route`，否则会有很多其他功能以某种方式帮助您构建项目。如果您的项目包含不太复杂的视图，那么您可以自由选择。