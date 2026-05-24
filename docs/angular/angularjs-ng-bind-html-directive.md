# angolajs | ng-bind-html 指令

> 原文:[https://www . geeksforgeeks . org/angular js-ng-bind-html-directive/](https://www.geeksforgeeks.org/angularjs-ng-bind-html-directive/)

AngularJS 中的 **ng-bind-html 指令**用于将 html 元素的 innerHTML 绑定到应用程序数据，并从 HTML 字符串中移除危险代码。ng-bind-html 指令必须有$sanitize 服务。所有 HTML 元素都支持它。

**语法:**

```ts
<element ng-bind-html="expression"> Contents... </element>

```

**示例:**这个示例说明了 ng-bind-html 指令。

```ts
<!DOCTYPE html>
<html ng-app="myApp">

<head>
    <title>ng-bind-html Directive</title>

    <script src=
"//ajax.googleapis.com/ajax/libs/angularjs/1.3.2/angular.min.js">
    </script>
    <script src=
"//ajax.googleapis.com/ajax/libs/angularjs/1.3.2/angular-sanitize.min.js">
    </script>

    <style>
        .green {
            color: green;
            font-size: 20px;
        }
    </style>
</head>

<body ng-controller="geek" style="text-align:center">

    <h1 style="color:green;">GeeksforGeeks</h1>
    <h2 style="">ng-bind-html Directive</h2>

    <p ng-bind-html="text"></p>

    <script>
        var myApp = angular.module("myApp", ['ngSanitize']);

        myApp.controller("geek", ["$scope", function($scope) {
            $scope.text =
            "<span class='green'> GeeksforGeeks</span> is the"
              + " computer science portal for geeks.";
        }]);
    </script>
</body>

</html>                    
```

**输出:**
![ngbindhtml](img/80df41d0f17ad00ed151ef12e259e437.png)