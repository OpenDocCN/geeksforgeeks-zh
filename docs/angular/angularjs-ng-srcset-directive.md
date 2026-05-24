# angolajs | ng-srcet 指令

> 哎哎哎:# t0]https://www . geeksforgeeks . org/angolajs-ng-srcet-directive/

AngularJS 中的 **ng-srcset 指令**用于指定< img >元素的 srcset 属性。它确保在评估完 AngularJS 之前不会产生错误的图像。由< img >和<源>元素支持。

**语法:**

```ts
<img ng-srcset="url"> </img> 

```

**示例:**

```ts
<!DOCTYPE html>
<html>
    <head>
        <title>ng-srcset Directive</title>
        <script src=
        "https://ajax.googleapis.com/ajax/libs/angularjs/1.4.2/angular.min.js">
        </script>

    </head>
    <body ng-app="app" style="text-align:center">
      <h1 style="color:green">GeeksforGeeks</h1>
      <h2>ng-srcset Directive</h2>
        <div ng-controller="geek">
            <img ng-srcset="{{pic}}" /><br><br><br>
        </div>
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
![ngsrcset](img/99a1c6dfa776bf980c244b00e5bf9359.png)