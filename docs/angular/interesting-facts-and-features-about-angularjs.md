# 关于 AngularJS 的有趣事实和特征

> 原文:[https://www . geesforgeks . org/interior-facts-and-features-about-angular js/](https://www.geeksforgeeks.org/interesting-facts-and-features-about-angularjs/)

![](img/dd66d4291904014874c5b53558c1f1e6.png)

让我们来了解一些关于 AngularJS 的有趣事实或特性:

**1。MVC 架构**
MVC 指的是模型视图架构，一个开发应用的产品例子。模型层处理应用程序的信息。视图层显示此信息，控制器连接模型和视图层。在琐碎的 MVC 结构和其他语言中，通常要求您将应用程序分成这些部分，并编写代码来将它们相互关联，老实说，这确实是一项令人厌倦的工作。在 AngularJS 中，您只需要将其划分为 MVC，Angular 负责其余部分。AngularJS 的这个特性为开发人员节省了大量的时间和繁琐的工作。

**2。独特的 AngularJS 路由器**
这个框架中的路由器有一个非常特殊的用法。与其他框架不同，它不观察 location.hash。在那些框架中，路由器观察并检查 location.hash，并在路由匹配后调用该函数。相反，它在 AngularJS 中充当服务器端路由器。

**3。带 HTML 的用户界面**
AngularJS 利用带 HTML 的用户界面辅助设计 UI，使其与其他框架略有不同。很难适应较短的标签。然而，Angular 使这些短标签易于使用和执行。它提供了一个本质上更好、更高效的界面，而不会增加任何成本。

**4。指令**
这是 AngularJS 的独特功能之一，也是它区别于其他框架的地方。授权允许开发人员和设计团队将实践分配给文档对象模型(DOM)，使软件架构师能够用 HTML 制作动态组件。

指令是在其动作之前带有前缀 ng-的属性。

*   ng-app 指令初始化应用程序。
*   ng-init 指令初始化数据。
*   ng-model 指令将控件的值连接到数据。

**示例:**

```ts
<div ng-app="" ng-init="firstName='Rahul'">

<p>Name: <input type="text" ng-model="firstName"></p>
<p>You wrote: {{ firstName }}</p>

</div>  
```

**5。范围**
除了指令，范围是 AngularJS 的另一个高度适用的功能。范围是指向模型的对象。它们相互连接控制器层和视图层。

**示例:**

```ts
angular.module('app', []).controller(
    function($scope) {
        $scope.message = "You're Awesome!"
    }
);
```

**说明:**从上面的代码可以看出，我们可以定义大量的变量，如姓名、话题、年龄等，并为其赋值。在 div 标签中，我们可以打印这些值。

**6。数据绑定**
AngularJS 是采用工程的模型-视图-控制器方法开发的。系统连接并绑定模型和视图。在接口中所做的更改将对应用程序结构的对象产生连续的影响，反之亦然。变化和后果是实时发生的。AngularJS 消除了使用 getElementById、addEventlistener 类编码的繁琐任务。

**7。依赖注入**
条件描述了代码如何相互接口，以及在特定部分所做的更改如何影响应用程序的其余部分。每一个改变也需要改变部分。在 AngularJS 中，您可以应用将条件视为外部组件的注射器，将段与它们各自的状态分开。Angular 的这一特性使其部分高度可重用，并且更容易验证和使用。依赖注入简化了测试过程，这意味着测试人员的负载更少。

**8。compatibility**
使用 Angular 这样的框架开发的应用程序也能在安卓、iOS 和主要移动操作系统上流畅运行。

**9。避免令人厌倦的工作**
开发新应用时，你可以避免重写代码。在 Angular 中，您可以简单地将代码复制粘贴到新的应用程序中，并制作一个实际的组件。AngularJS 编写了大部分代码，让用户免于不必要的麻烦。

**10。由谷歌开发**T2】谷歌是新时代的四大巨头之一。AngularJS 由一群极具天赋的专家维护和更新，他们意识到并识别系统中的问题和缺陷。此外，有了这种支持和定期更新，您不必担心框架很快就会过时。

**11 时。高性能**
大量的变量可以帮助开发人员/设计人员使他们的应用程序更加敏捷。