# 如何使用 Angular UI Bootstrap 进行分页？

> 原文:[https://www . geeksforgeeks . org/如何使用-angular-ui-bootstrap/](https://www.geeksforgeeks.org/how-to-make-pagination-using-angular-ui-bootstrap/)

在本文中，我们将看到如何使用 Angular UI 引导程序制作下拉菜单

Angular UI Bootstrap 是 Angular UI 开发人员创建的一个 Angular JS 框架，用于提供更好的 UI，可以轻松使用。

**语法:**

```ts
<div uib-pagination></div>
```

**从链接下载安古拉瑞:**

```ts
https://angular-ui.github.io/bootstrap
```

**进场:**

*   首先，添加项目所需的 Angular UI 引导脚本。

> <脚本 src = " https://Ajax . googleapis . com/Ajax/libs/angular js/1 . 6 . 1/angular-animate . js "></脚本>
> <脚本 src = " https://Ajax . googleapis . com/Ajax/libs/angular js/1 . 6 . 1/angular-sanitar . js "></脚本>
> T13

*   使用它的 UIBootStrap 类进行分页，这将设置分页的 UI 外观。
*   现在使用不同的类进行不同类型的分页并运行代码。

**示例:**

## 超文本标记语言

```ts
<!DOCTYPE html>
<html ng-app="gfg">
  <head>

    <!-- Adding CDN scripts required for our page -->
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.1/angular.js">
    </script>
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.1/angular-animate.js">
    </script>
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.1/angular-sanitize.js">
    </script>
    <script src=
"https://angular-ui.github.io/bootstrap/ui-bootstrap-tpls-2.5.0.js">
    </script>

    <script>
      // Adding Modules
      angular.module('gfg', ['ngAnimate', 'ngSanitize', 'ui.bootstrap']);
      angular.module('gfg').controller('pagination', function ($scope) {
        $scope.totalItems = 64;
        $scope.currentPage = 4;
        });
    </script>
    <link href=
"https://netdna.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"
          rel="stylesheet">
  </head>
  <body>
    <div ng-controller="pagination">

      <!-- making a pagination -->
       <ul uib-pagination total-items="totalItems" 
           ng-model="currentPage" 
           ng-change="pageChanged()"></ul>
       <br>
    <ul uib-pagination boundary-links="true" 
        total-items="totalItems" 
        ng-model="currentPage" 
        class="pagination-sm" 
        previous-text="‹" 
        next-text="›" 
        first-text="«" 
        last-text="»"></ul>
    </div>
  </body>
</html>
```

**输出:**

![](img/0d4f8f95193a300a0e91a97f3f8a8137.png)

**参考:**T2】https://angular-ui.github.io/bootstrap/#!#pagination