# 如何使用 Angular UI Bootstrap 进行评级？

> 原文:[https://www . geeksforgeeks . org/如何使用 angular-ui-bootstrap/](https://www.geeksforgeeks.org/how-to-make-rating-using-angular-ui-bootstrap/)

在本文中，我们将看到如何使用 Angular UI 引导程序制作下拉菜单。

Angular UI Bootstrap 是 Angular UI 开发人员创建的一个 Angular JS 框架，用于提供更好的 UI，可以轻松使用。

**语法:**

```ts
<div uib-rating></div>
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

*   用它的引导类进行评级，引导类将设置评级的用户界面外观。
*   现在使用不同的类进行不同类型的评级，并运行代码。

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
    <link href=
"https://netdna.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"
        rel="stylesheet">

    <script>

        // Adding Modules
        angular.module('gfg', ['ngAnimate', 'ngSanitize', 'ui.bootstrap']);
        angular.module('gfg').controller('rating', function ($scope) {
            $scope.rate = 4;
            $scope.max = 12;
            $scope.isReadonly = false;
            $scope.hov = function (value) {
                $scope.over = value;
                $scope.per = 100 * (value / $scope.max);
            };
        });
    </script>
</head>

<body>
    <div ng-controller="rating">

        <!-- making a rating -->
        <div class="loumn">

            <span uib-rating ng-model="rate" max="max" 
                read-only="isReadonly" on-hover="hov(value)"
                on-leave="over = null" titles=
                "['a','b','c','d','e','f','g','h','i','j','k','l']"
                aria-labelledby="default-rating">
            </span>

            <span class="label"
                ng-class="{'label-warning': per<30, 
                    'label-info': per>=30 && per<70, 
                    'label-success': per>=70}"
                ng-show="over && !isReadonly">{{per}}%</span>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/0916f25d3421c224c97a4951f8769773.png)

**参考:**[](https://angular-ui.github.io/bootstrap/#!#popover)**[https://angular-ui.github.io/bootstrap/#!#rating](https://angular-ui.github.io/bootstrap/#!#rating)**