# 脊线 js 和角形 js 的区别

> 原文:[https://www . geesforgeks . org/主干-js 和-angular-js 之间的差异/](https://www.geeksforgeeks.org/difference-between-backbone-js-and-angular-js/)

AngularJS 被认为更具特色，更全面地满足了客户的需求(Upwork、iStockPhoto、Climate、PayPal 都是用 precision 构建的)，尽管任何 Spine JS 设计师都会说 Spine 也包含了一大堆有价值的亮点。Angular 有内置的坐标实用程序，它可以在最近某个时候帮助批准客户端输入，并将其处理或发送到服务器。Angular 致力于研究工具。角度检查是否有任何变化，并升级比较字段。Angular 包括一个流行的插件，它结合了办公室来形成动画。主干允许很好地集成第三方库。信息官员的骨干就业观察站(它观察模型)。主干网的特点是，在支持模型的安排上，可以扩展其合理性，并且可以看到彼此的彻底改变。主干可能与其他布局电机(不止一个)配合良好。他们都背对着与浏览器网址相关联的深刻连接。他们有一个稳定开放的应用编程接口。他们可以使用另类模块定义库。他们有一个专门的插件源出现在框架的动态生态系统中。它们都支持鲍尔信实管理；他们有一个风险生成器，让工程师自然地建立一个不用的风险，而利用内置的工具。
[**angular . js**](https://www.geeksforgeeks.org/introduction-to-angularjs/)angular js 可能是一个特别有能力的 JavaScript 系统。它用于单页应用程序(SPA)风险。它用额外的属性放大了 HTML DOM，并使其对客户端活动更加敏感。AngularJS 是一个开源的，完全免费的，被世界上成千上万的设计师使用。它是在 Apache 许可证改编 2.0 下授权的。
Angular 是一个开源的 MVC JavaScript(编程方言)系统，通过广告编程视图/模型同步来重新排列 web 改进。扩展到双向官方，精确是轻量级的，支持所有主要的浏览器，并为制作可测试的 JavaScript 代码而构建。miko Hevery 制作了 angular(http://misko . Hevery . com/)。来自 Angular 网站:是 HTML 在构建网络应用程序时被概述的可能性。它为你的应用提供了管道，所以你将专注于你的应用做什么，而不是如何督促你的网络浏览器做你需要的事情。
**例:**

## java 描述语言

```ts
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf 8">
    <title>Geeksforgeeks</title>

    <script src=
"https://code.angularjs.org/1.6.9/angular.js">
    </script>
</head>

<body ng-app="app">
    <h1 ng-controller="HelloWorldCtrl">
        {{message}}
    </h1>

    <script>
        angular.module("app", []).controller(
            "HelloWorldCtrl", function($scope) {
                $scope.message="GeeksforGeeks"
            }
        )
    </script>
</body>

</html>
```

**输出:**

```ts
GeeksforGeeks

```

**angular . js 的特征:**

*   **REST Easy:** Restful 活动正迅速成为从服务器到客户端通信的标准。在一行 JavaScript 中，您将能够快速地与服务器对话，并获得您希望与网页关联的数据。AngularJS 把这变成了一个基本的 JavaScript 抗议，就像模型一样，模仿了 MVVM 的设计。

*   **MVVM 救援队:**将对话模型化为视图模型对象(通过一种叫做$scope 抗议的方式)，这种方式可以调整模型的变化。此时，这些可以由 Sees 来传达和呈现，Sees 是传达您的代码的 HTML。Sees 可以利用$routeProvider 抗议来控制，所以你可以深度链接和组织你的 Sees 和 Controllers，把它们变成安全的 URL。此外，AngularJS 还提供了无状态控制器，可以初始化和控制$scope 抗议。
*   **数据绑定和依赖注入:**MVVM 设计中的所有内容都会在用户界面上进行交流，无论什么时候发生变化。这消除了对包装器、获取器/设置器或过程语句的需求。AngularJS 处理所有这些，所以您将像使用 JavaScript 原语一样本质地表达您的信息，比如集群，或者像您希望的那样通过自定义排序来表达您的信息。因为一切都是随后发生的，所以您将在 AngularJS 受益能力中查询您的条件作为参数，而不是一个巨大的 basic()调用来执行您的代码。
*   **扩展 HTML:** 现在建立的大多数网站都是标签的怪物排列，语义清晰度很小。您希望形成广泛而详尽的 CSS 类来精确地考虑 DOM 中的每个问题。有了精确，你将能够像处理 XML 一样处理你的 HTML，给你无尽的标签和特性。精确实现了这一点，通过它的 HTML 编译器和利用命令来触发基于你新创建的句子结构的行为。

**主干 js:** 它可能是一个基于 MVC 的 Javascript 系统，在为扩展的应用程序编写隐蔽的代码时会让你与众不同。用主干网的话说，主干网通过给模型提供关键值的官方和定制场合，给集合提供丰富的可枚举能力的应用编程接口，给视图提供解释性的场合，并通过一个宁静的 JSON 接口将其与现有的应用编程接口连接，从而给网络应用程序提供结构。当在一个包含部分 JavaScript 的 web 应用程序上工作时，你学到的主要事情之一是停止将你的信息绑定到 DOM。让 JavaScript 应用程序总结为错综复杂的 jQuery 选择器和回调堆也很简单，所有这些都试图快速地将信息保存在 HTML 用户界面、JavaScript 基本原理和服务器上的数据库之间的匹配中。对于富有的客户端应用程序，更有条理的方法通常是支持的。
有了主干网，您可以像模型一样与您的信息对话，这些信息可以被制作、批准、销毁，并保存到服务器上。无论用户界面活动在什么时候导致节目属性改变，节目都会触发“改变”事件；所有显示模型状态的视图都可以被告知发生了变化，这样它们就可以适当地回复，用现代数据重新呈现自己。在一个包装好的主干应用程序中，您不必编写进入 DOM 的棒代码来发现一个具有特定 id 的组件，并在物理上彻底检查 HTML 当显示发生变化时，看到的本质上是升级自己。从哲学上来说，主干网是一种努力，寻找一组可以忽略的数据结构(模型和集合)和客户端接口(sees 和 URL)原语，这些原语在用 JavaScript 构建网络应用程序时基本上是有价值的。在一个支配一切、为你决定一切的系统司空见惯的环境中，许多库要求你的位置被重组以适应主干网
**示例:**

## java 描述语言

```ts
<!DOCTYPE html>
<html>
    <head>
        <script src=
"https://code.jquery.com/jquery-3.1.0.min.js"></script>
        <script src=
"https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.8.3/underscore-min.js">
       </script>

        <script src=
"https://cdnjs.cloudflare.com/ajax/libs/backbone.js/1.3.3/backbone-min.js">
        </script>

        <script>
            $( function(){
                ( function(){
                    var View = Backbone.View.extend( {
                        "el": "body",
                        "template": _.template( "
<p>GeeksforGeeks</p>
" ),

                        "initialize": function(){
                            this.render();
                        },
                        "render": function(){
                            this.$el.html( this.template() );
                        }
                    } );

                    new View();
                })()
            } );
        </script>
    </head>
    <body>
    </body>
</html>
```

**输出:**

```ts
GeeksforGeeks

```

**主干网特色:**

*   **事件驱动的通信:**用 jQuery 这样的系统做小而流畅的 web 应用很简单。无论如何，当扩展开发时，jQuery 声明和回调变得越来越复杂，并且分布在整个 put 中。代码变得越来越混乱和难以阅读。Backbone.js 通过在 see 和模型(以及我们目前为了省力而忽略的其他组件)之间提供事件驱动的通信来简化这一点。您可以将特定场合的观众加入到模型的任何属性中，这为您提供了异常细致的控制，让您可以在场景中更改内容。
*   **与后端同步:**backbone . js 中的模型可以毫不费力地绑定到后端。开箱即用的系统为宁静的应用编程接口提供了惊人的支持，因为模型可以勾勒出一个放松的端点。如果应用编程接口计划准确，spine 目前被安排专门进行研究、编写和删除操作(通过 get、POST 和 Delete)。
*   **通过以下约定实现的可维护性:**传统是一种特殊的方式来呈现一种通用的编码方式，而不需要提出一套广泛的编码方法。在 Visual.ly 中，我们发现尽管有不同的人在代码上进行协作，但是 backbone.js 对于保持一个干净的代码库是特别支持的。这里的神秘酱是迟缓。越遵守(少数)主干约定，代码就越少，反过来，代码就越标准化和清晰。

<figure class="table">

| 棱角分明。射流研究… | 骨干 js |
| --- | --- |
|  |  |
| AngulJS is a framework. | BackboneJS is a lightweight and easy-to-use library. |
| AngularJS can be the UI system in JS, but it is based on Typescript. | Backstage JS can be a UI system in JS based on MVC (Model View Controller) design pattern. |
| Dynamic and rich web pages for SPA applications. | Provide authoritative and customized occasion functions for network applications. |
| Support integration with different systems, tools and IDEs. | Support integration with different systems and network applications, because it is easy to use. |
| In addition, it is licensed under the Massachusetts Institute of Technology and maintained by Google. | It's authorized by MIT. |

</figure>