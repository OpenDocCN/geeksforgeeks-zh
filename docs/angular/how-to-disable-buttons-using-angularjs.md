# 如何使用 AngularJS 禁用按钮？

> 原文:[https://www . geeksforgeeks . org/如何禁用按钮-使用-angularjs/](https://www.geeksforgeeks.org/how-to-disable-buttons-using-angularjs/)

有时我们需要禁用点击事件上的按钮、链接。在本文中，我们将看到如何在 AngularJS 的帮助下做到这一点。

**进场:**

*   方法是使用 **ng-disabled 指令**禁用特定按钮。
*   在第一个示例中，单击可禁用单个按钮，在第二个示例中，单击可禁用多个按钮。

**例 1:**

## 超文本标记语言

```tshtml
<!DOCTYPE HTML> 
<html> 

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.2.13/angular.min.js">
    </script>

    <script>
        var myApp = angular.module("app", []);
        myApp.controller("controller", function($scope) {
            $scope.disabledFlag = false;
            $scope.disableIt = function() { 
                $scope.disabledFlag = true;
            };
        });
    </script>
</head>

<body style = "text-align:center;">
    <h1 style = "color:green;">  
        GeeksForGeeks  
    </h1>

    <p>
        Disable the button in AngularJS
    </p>

    <div ng-app="app">  
        <div ng-controller="controller">
            <button ng-click='disableIt()' 
                ng-disabled='disabledFlag' >
                Click to disable
            </button>
        </div>
    </div>
</body>   

</html>
```

**输出:**

![](img/77f00ca179f9d506809114a7a224b2b4.png)

**例 2:**

## 超文本标记语言

```tshtml
<!DOCTYPE HTML> 
<html> 

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.2.13/angular.min.js">
    </script>

    <script>
        var myApp = angular.module("app", []);
        myApp.controller("controller", function($scope) {
            $scope.disabledFlag1 = false;
            $scope.disableIt1 = function() { 
                $scope.disabledFlag1 = true;
            };
            $scope.disabledFlag2 = false;
            $scope.disableIt2 = function() { 
                $scope.disabledFlag2 = true;
            };
            $scope.disabledFlag3 = false;
            $scope.disableIt3 = function() { 
                $scope.disabledFlag3 = true;
            };
            $scope.disabledFlag = false;
            $scope.disableIt = function() { 
                $scope.disabledFlag1 = true;
                $scope.disabledFlag2 = true;
                $scope.disabledFlag3 = true;
            };
        });
    </script>
</head>

<body style = "text-align:center;">
    <h1 style = "color:green;">  
        GeeksForGeeks  
    </h1>

    <p>
        Disable the button in AngularJS
    </p>

    <div ng-app="app">  
        <div ng-controller="controller">
            <button ng-click='disableIt1()' 
                ng-disabled='disabledFlag1' >
                disable it
            </button>
            <button ng-click='disableIt2()' 
                ng-disabled='disabledFlag2' >
                disable it
            </button>
            <button ng-click='disableIt3()' 
                ng-disabled='disabledFlag3' >
                disable it
            </button>
            <br>
            <br>
            <button ng-click='disableIt()' 
                ng-disabled='disabledFlag' >
                disable All
            </button>
        </div>
    </div>
</body>   

</html>
```

**输出:**

![](img/0b6ea47982e99c2908a044fb8ddcc0d4.png)