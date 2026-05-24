# AngularJS | ng-class-奇数指令

> 原文:[https://www . geeksforgeeks . org/angular js-ng-class-odd-direction/](https://www.geeksforgeeks.org/angularjs-ng-class-odd-directive/)

AngularJS 中的 **ng 类奇数指令**用于在 HTML 元素的每个奇数外观上指定 CSS 类。它用于动态绑定每个奇数 HTML 元素上的类。如果 ng-class-odd 指令中的表达式返回 true，则只添加该类，否则不添加。ng 类奇数指令需要 ng-repeat 指令才能工作。所有 HTML 元素都支持它。

**语法:**

```ts
<element ng-class-odd="expression"> Contents... </element> 
```

**示例:**本示例使用 ng-class-odd Directive 选择奇数元素并添加一些 CSS 样式。

```ts
<!DOCTYPE html>
<html>

<head>
    <title>ng-class-odd Directive</title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.4.2/angular.min.js">
    </script>

    <style type="text/css">
        .index {
            color: white;
            background-color: green;
        }
    </style>
</head>

<body ng-app="app" style="padding:20px">

    <h1 style="color:green">GeeksforGeeks</h1>
    <h2>ng-class-odd Directive</h2>

    <div ng-controller="geek">
        <table>
            <thead>
            <th>sorting techniques:</th>
            <tr ng-repeat="i in sort">
                <td ng-class-odd="'index'">
                    {{i.name}}
                </td>
            </tr>
            </thead>
        </table>
    </div>

    <script>
        var app = angular.module("app", []);
        app.controller('geek', ['$scope', function ($scope) {
            $scope.sort = [
                { name: "Merge sort" }, 
                { name: "Quick sort" },
                { name: "Insertion sort" }, 
                { name: "Bubble sort" }
            ];     
        }]);
    </script>
</body>

</html>                    
```

**输出:**
![ngclassodd](img/dfb4aa0a6e7f80221c7e5bad05732273.png)