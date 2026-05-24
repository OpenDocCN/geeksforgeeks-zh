# 如何使用 AngularJS 重新加载或重新渲染整个页面？

> 原文:[https://www . geeksforgeeks . org/如何使用-angularjs/](https://www.geeksforgeeks.org/how-to-reload-or-re-render-the-entire-page-using-angularjs/) 重新加载或重新渲染整个页面

在使用 AngularJS 时，我们可能会遇到希望用户切换上下文并重新呈现所有内容的时候。AngularJS 提供了一个方法，通过这个方法，我们可以重新呈现甚至重新加载整个页面。因此，在本文中，我们将看到如何重新加载路由，而不仅仅是重新加载整个页面或应用程序，因为刷新整个页面只是为了一些偶尔会出现问题的小机会，我们还将看到如何从服务器或从缓存本身重新加载整个页面。AngularJS 主要提供了两种不同的重新加载和刷新方法

**使用 reload()方法:**角路由服务 **reload()方法**是在我们只想重载当前路由而不是让整个应用程序重载或刷新时使用的。假设路由的控制器有在控制器实例化时被调用的服务，并且当某些情况发生时需要重新调用那些完全相同的服务来刷新数据。所以我们能做的基本上是最小化所有这些重装任务，我们可以直接调用 **$route.reload()** 。这不会刷新整个页面，但只会重新加载将重新实例化控制器的路由，从而调用服务。

**例:**

## Javascript

```ts
app.controller('ControllerName',
               ['$scope', '$route', function($scope, $route) {
    $scope.reloadRoute = function() {

        // Reload only the route which will re-instantiate
        $route.reload();
    };
}]);
```

[**使用 location.reload()方法**](https://www.geeksforgeeks.org/html-dom-location-reload-method/)**:****location . reload()方法**用于刷新或重新加载整个页面，可选择强制重新下载内容。此方法给出的结果与我们使用刷新或重新加载按钮时的结果相同。它只是重置了我们整个网站的状态。默认情况下，此方法从缓存中加载页面，当我们将 **forceGet 属性**设置为 true 时，页面将从服务器中重新加载。此方法没有任何返回类型。

**语法:**

```ts
location.reload(forceGet)
```

**示例:**forceGet 参数是一个可选参数，应该只在我们想要强制整个网站从服务器重新加载时使用。如果没有 forceGet 属性，网站将从缓存中重新加载。

## Javascript

```ts
function locationreload() {

        // To reload the entire page from the server
        location.reload();      
        }
```