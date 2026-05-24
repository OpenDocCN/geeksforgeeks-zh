# angolajs | ng-src 指令

> 原文:[https://www.geeksforgeeks.org/angularjs-ng-src-directive/](https://www.geeksforgeeks.org/angularjs-ng-src-directive/)

AngularJS 中的 **ng-src 指令**用于指定< img >元素的 src 属性。它确保在评估完 AngularJS 之前不会产生错误的图像。它由< img >元素支持。

**语法:**

```ts
<img ng-src="url"> </img> 

```

**示例:**

```ts
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <title>ng-src Directive</title>
        <script src=
        "https://ajax.googleapis.com/ajax/libs/angularjs/1.4.2/angular.min.js">
        </script>

    </head>
    <body ng-app="app" style="text-align:center">
      <h1 style="color:green">GeeksforGeeks</h1>
      <h2>ng-src Directive</h2>
        <div ng-controller="geek">
            <img ng-src="{{pic}}" /><br><br><br>
        <script>
            var app = angular.module("app", []);
            app.controller('geek', ['$scope', function ($scope) {
                $scope.pic = 
  "https://media.geeksforgeeks.org/wp-content/uploads/20190328034223/ngimg1.png";
            }]);
        </script>
    </body>
</html>
```

**输出:**

![](img/2454e3a186a48c48f4c94ca074caded5.png)