# 如何使用 Angular UI Bootstrap 制作 Popover？

> 原文:[https://www . geeksforgeeks . org/如何使用 angular-ui-bootstrap/](https://www.geeksforgeeks.org/how-to-make-popover-using-angular-ui-bootstrap/)

在本文中，我们将看到如何使用 Angular UI 引导程序制作下拉菜单

Angular UI Bootstrap 是 Angular UI 开发人员创建的一个 Angular JS 框架，用于提供更好的 UI，可以轻松使用。

**语法:**

```ts
<div uib-popover></div>
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

*   用它的 UIBootStrap 类创建弹出窗口，这将设置弹出窗口的 UI 外观。
*   现在使用不同的类生成不同类型的 popover 并运行代码。

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
      angular.module('gfg').controller('popover', function ($scope) {
        $scope.totalItems = 64;
        $scope.currentPage = 4;
        });
    </script>
    <link href=
"https://netdna.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" 
          rel="stylesheet">
  </head>
  <body>
    <div ng-controller="popover">

      <!-- making a popover -->
      <div class="form-group">
        <label>Name:</label>
        <input type="text" 
               ng-model="dynamicPopover.content" 
               class="form-control">
      </div>
      <div class="form-group">
        <label>Language:</label>
        <input type="text" 
               ng-model="dynamicPopover.title"
               class="form-control">
      </div>

    </div>
  </body>
</html>
```

**输出:**

![](img/1db8ab0eb40d53c9e73e9387a5a96e61.png)

**参考:**[**https://angular-ui.github.io/bootstrap/#!#popover**](https://angular-ui.github.io/bootstrap/#!#popover)