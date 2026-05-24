# 如何使用$scope。AngularJS 中的$apply()？

> 原文:[https://www . geesforgeks . org/how-use-scope-apply-in-angularjs/](https://www.geeksforgeeks.org/how-to-use-scope-apply-in-angularjs/)

在本文中，我们将讨论$apply()函数&如何在 angularjs 中使用它。在 AngularJS 中，$apply()函数用于计算 AngularJS 上下文之外的表达式(浏览器 DOM Events，XHR)。此外，$apply 的引擎盖下有$digest，每当调用$apply()来更新数据绑定时，最终都会调用它。我们举个例子来更好的理解。

**不使用$scope。$apply()函数:**在下面的代码中，可以看到我们有两个按钮，但是一个按钮有一个 ng-click 事件来更新名称，而另一个按钮有一个标准的 JavaScript 监听器来更新名称。因此，您可以看到，当单击第一个按钮时，名称从“GFG”更改为“GFG 岩石”，但当单击第二个按钮时，由于缺少$scope，名称不会更新为“Geeks”。$应用呼叫。

## 超文本标记语言

```ts
<!DOCTYPE html>
<html>

<head>
    <title>$apply() Function in AngularJs</title>
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js">
    </script>

    <script type="text/javascript">
        var app = angular.module("applyApp", []);
        app.controller("applyCtrl", function ($scope) {
            $scope.currentName = "GFG";
            $scope.updatedName = function () {
                $scope.currentName = "GFG Rocks";
            };

            // Event listener added
            var event = document.getElementById("btnapply");
            event.addEventListener("click", function () {

                // To update name on rootScope forcefully,
                // use $apply function
                $scope.currentName = "Geeks";
            });
        });
    </script>
</head>

<body>
    <div ng-app="applyApp" ng-controller="applyCtrl">
        <h2>$apply() Function in AngularJs</h2>
        <input type="button" 
            value="Click to Update Name" 
            ng-click="updatedName()" />

        <input type="button" 
            value="Click to Update Name forcefully." 
            id="btnapply" />

        <span style="color: Red">{{currentName}}</span>
    </div>
</body>

</html>
```

**Output:**
![](img/e8ae60a8bc53589ccdb873fc9d1f0099.png)

**使用$作用域。$apply()调用:**在上面的代码中，可以看到我们有两个按钮，但是一个按钮有一个 ng-click 事件来更新名称，而另一个按钮有一个标准的 JavaScript 侦听器来更新名称。因此，您可以看到，当单击第一个按钮时，名称从“GFG”更改为“GFG 岩石”，当单击第二个按钮时，由于$scope 的存在，名称更新为“极客”。$在此应用调用。

## 超文本标记语言

```ts
<!DOCTYPE html>
<html>

<head>
    <title>$apply() Function in AngularJs</title>
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js">
    </script>

    <script type="text/javascript">
        var app = angular.module("applyApp", []);
        app.controller("applyCtrl", function ($scope) {
            $scope.currentName = "GFG";
            $scope.updatedName = function () {
                $scope.currentName = "GFG Rocks";
            };

            // Event listener added
            var event = document.getElementById("btnapply");
            event.addEventListener("click", function () {
                $scope.$apply(() => {

                    // To update name on rootScope 
                    // forcefully, use $apply function
                    $scope.currentName = "Geeks";
                });
            });
        });
    </script>
</head>

<body>
    <div ng-app="applyApp" ng-controller="applyCtrl">
        <h2>$apply() Function in AngularJs</h2>
        <input type="button" 
            value="Click to Update Name" 
            ng-click="updatedName()" />

        <input type="button" 
            value="Click to Update Name forcefully." 
            id="btnapply" />

        <span style="color: Red">{{currentName}}</span>
    </div>
</body>

</html>
```

**Output:**
![](img/8a22b52544171b9da40ddab3d637d453.png)