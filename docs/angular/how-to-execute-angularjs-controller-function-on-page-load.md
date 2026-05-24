# 页面加载时如何执行 AngularJS 控制器功能？

> 原文:[https://www . geesforgeks . org/how-execution-angularjs-controller-function-on-page-load/](https://www.geeksforgeeks.org/how-to-execute-angularjs-controller-function-on-page-load/)

任务是使用 AngularJS 在页面加载时执行/调用一个 JS 函数。该功能可用于执行初始化。

在 AngularJS 中调用函数或在页面加载时初始化单个值非常容易。AngularJS 为我们提供了一个专门的指令来完成这个特定的任务。这是 ng-init 指令。
**语法:**

```ts
<element ng-init="function()"> Contents... </element>

```

**示例 1:** 在本例中，我们将在页面加载时调用一个函数来初始化一个变量。

```ts
<html ng-app="myApp">
<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.7.8/angular.min.js">
    </script>
</head>

<body ng-controller="MyController">

    <!-- calling the firstFunction to 
         initialize gfg variable -->
    <center ng-init="firstFunction(this)">

        <!-- gfg variable with no value initially -->
        <h1 style="color: green;">{{gfg}}</h1>
    </center>
</body>

<script type="text/javascript">
    var myApp = angular.module('myApp', []);
    myApp.controller('MyController', ['$scope', function($scope) {

        // Function to be called on page load
        $scope.firstFunction = function($scope) {

            // We need $scope argument as we are
            // altering the variables defined in
            // the $scope
            $scope.gfg = "GeeksForGeeks"
        }
    }]);
</script>
</html>
```

**输出:**页面加载时调用函数，变量 gfg 的值设置为 GeeksForGeeks。
T3】

**示例 2:** 在本例中，我们将为变量 gfg 分配一个对象并使用它。

```ts
<html ng-app="myApp">
<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.7.8/angular.min.js">
    </script>
</head>

<body ng-controller="MyController">

    <!-- Calling the firstFunction to 
         initialize gfg variable -->
    <center ng-init="firstFunction(this)">

        <!-- gfg variable as an object -->
        <h1 style="color: green;">{{gfg.name}}</h1>
        <h3 style="color: green;">{{gfg.location}}</h3>
    </center>
</body>

<script type="text/javascript">
    var myApp = angular.module('myApp', []);
    myApp.controller('MyController', ['$scope', function($scope) {

        // Function to be called on page load
        $scope.firstFunction = function($scope) {

            // We need $scope argument as we are
            // altering the variables defined in
            // the $scope

            // Assigning an object to the gfg variable
            $scope.gfg = {
                name: "GeeksForGeeks",
                location: "India"
            }
        }
    }]);
</script>

</html>
```

**输出:**变量“gfg”初始化成功。
T3】

**示例 3:** 在本例中，我们将从 ng-init 指令直接初始化一个变量。

```ts
<html ng-app="myApp">
<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.7.8/angular.min.js">
    </script>
</head>

<body ng-controller="MyController">

    <!-- initializing the gfg variable to 
         'GeeksForGeeks' -->
    <center ng-init="gfg='GeeksForGeeks'">
        <h1 style="color: green;">{{gfg}}</h1>
    </center>
</body>

<script type="text/javascript">
    var myApp = angular.module('myApp', []);
    myApp.controller('MyController', ['$scope', function($scope) {

    }]);
</script>

</html>
```

**输出:**在页面加载时，变量 gfg 被赋予值“GeeksForGeeks”。
T3】