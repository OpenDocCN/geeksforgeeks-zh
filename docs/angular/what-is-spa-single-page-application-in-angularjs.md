# AngularJS 中的 SPA(单页应用)是什么？

> 原文:[https://www . geeksforgeeks . org/what-is-spa-单页应用 in-angularjs/](https://www.geeksforgeeks.org/what-is-spa-single-page-application-in-angularjs/)

传统上，应用程序是多页面应用程序，每次点击都会从服务器加载一个新页面。这不仅耗时，而且增加了服务器负载，使网站运行速度变慢。AngularJS 是基于双向 UI 数据绑定的基于 JavaScript 的前端 web 框架，用于设计单页应用程序。单页应用程序是加载单个 HTML 页面的 web 应用程序，每次单击鼠标时，只更新页面的一部分，而不是整个页面。在此过程中，页面不会重新加载或将控制转移到另一个页面。这确保了高性能和更快地加载页面。大多数现代应用程序都使用 SPA 的概念。在 SPA 中，整个数据在开始时从服务器发送到客户端。当客户端点击网页上的某些部分时，只从服务器获取所需的信息部分，页面被动态重写。这使得服务器上的负载更小，并且具有成本效益。SPAs 使用 AJAX 和 HTML5 来创建一个流畅且响应迅速的 Web 应用程序，大部分工作发生在客户端。脸书、Gmail、Twitter、Google Drive、网飞等热门应用都是 SPA 的例子。
**优势:**

*   **团队协作**
    当多个开发人员在同一个项目中工作时，单页应用程序非常出色。它允许后端开发人员专注于应用编程接口，而前端开发人员可以专注于基于后端应用编程接口创建用户界面。
*   **缓存**
    应用程序向服务器发送一个请求，并将收到的所有信息存储在缓存中。当客户端的网络连接性很差时，这证明是有益的。
*   **快速响应**
    由于只有部分页面是动态加载的，所以提高了网站的速度。
*   **调试更容易**
    使用 chrome 调试单页应用程序更容易，因为这类应用程序是使用类似 AngularJS Batarang 和 React 这样的开发工具开发的。
*   **线性用户体验**
    浏览或导航网站很容易。

**缺点:**

*   **SEO 优化**
    spa 提供较差的 SEO 优化。这是因为单页应用程序在 JavaScript 上运行，并在服务器上一次加载数据。网址不会改变，不同的页面没有唯一的网址。因此，相对于传统的服务器渲染页面，搜索引擎很难对 SPA 网站进行索引。
*   **浏览器历史**
    一个 SPA 不保存用户在网站内的状态转换。浏览器只保存以前的页面，不保存状态转换。因此，当用户单击后退按钮时，他们不会被重定向到网站的先前状态。为了解决这个问题，开发人员可以为他们的 SPA 框架配备 HTML5 历史应用编程接口。
*   **安全问题**
    单页应用对跨站点脚本的免疫力较低(XSS)，并且由于没有加载新页面，黑客可以轻松访问网站并在客户端注入新脚本。
*   **内存消耗**
    由于 SPA 可以长时间运行，有时一次运行几个小时，因此需要确保应用程序消耗的内存不会超过其需求。否则，内存不足的用户可能会面临严重的性能问题。
*   **禁用 Javascript**
    开发人员需要为用户在禁用 Javascript 的浏览器上访问网站信息写出想法。

**什么时候用 SPA**
数据量小，网站需要动态平台的时候 SPA 就好。对于移动应用来说，这也是一个不错的选择。但主要依赖电子商务应用等搜索引擎优化的企业必须避免单页应用，选择 MPAs。

```ts
<!DOCTYPE html>
<!--ng-app directive tells AngularJS that myApp
    is the root element of the application -->
<html ng-app="myApp">
    <head>
        <!--import the angularjs libraries-->
        <script src=
"https://cdnjs.cloudflare.com/ajax/libs/angular.js/1.4.7/angular.min.js">
      </script>
        <script src=
"https://cdnjs.cloudflare.com/ajax/libs/angular.js/1.4.7/angular-route.min.js">
      </script>
    </head>
    <body>
        <!--hg-template indicates the pages 
            that get loaded as per requirement-->
        <script type="text/ng-template" 
                id="first.html">
            <h1>First Page</h1>
            <h2 style="color:green">
                Welcome to GeeksForGeeks
            </h2>
            <h3>{{message}}</h3>
        </script>
        <script type="text/ng-template" 
                id="second.html">
            <h1>Second Page</h1>
            <h2 style="color:green">
                Start Learning With GFG
            </h2>
            <h3>{{message}}</h3>
        </script>
        <script type="text/ng-template"
                id="third.html">
            <h1>Third Page</h1>
            <h2 style="color:green">
                Know about us
            </h2>
            <h3>{{message}}</h3>
        </script>
        <!--hyperlinks to load different 
              pages dynamically-->
        <a href="#/">First</a>
        <a href="#/second">Second</a>
        <a href="#/third">Third</a>
        <!--ng-view includes the rendered template of
            the current route into the main page-->
        <div ng-view></div>
        <script>
            var app = angular.module('myApp', []);
            var app = angular.module('myApp', ['ngRoute']);
            app.config(function($routeProvider) {
            $routeProvider

            .when('/', {
            templateUrl : 'first.html',
            controller : 'FirstController'
            })

            .when('/second', {
            templateUrl : 'second.html',
            controller : 'SecondController'
            })

            .when('/third', {
            templateUrl : 'third.html',
            controller : 'ThirdController'
            })

            .otherwise({redirectTo: '/'});
            });

            <!-- controller is a JS function that maintains
     application data and behavior using $scope object -->
            <!--properties and methods can be attached to the
                $scope object inside a controller function-->

            app.controller('FirstController', function($scope) {
            $scope.message = 'Hello from FirstController';
            });

            app.controller('SecondController', function($scope) {
            $scope.message = 'Hello from SecondController';
            });

            app.controller('ThirdController', function($scope) {
            $scope.message = 'Hello from ThirdController';
            });
        </script>
    </body>
</html>
```

**输出:**
![](img/6e93ab0df2d24560289bfaede97f2d05.png)

![](img/97d6171489344b3a4d5147830e72536d.png)

![](img/737686ba7b082c6b78d177379d247a8b.png)