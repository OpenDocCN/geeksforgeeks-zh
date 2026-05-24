# 使用 AngularJS 点击后如何改变按钮颜色？

> 原文:[https://www . geeksforgeeks . org/点击后如何更改按钮颜色-使用-angularjs/](https://www.geeksforgeeks.org/how-to-change-the-button-color-after-clicking-it-using-angularjs/)

创建了一个 HTML 按钮，任务是在 AngularJS 的帮助下改变按钮按下时的背景颜色。

**方法:**在这种方法中，我们将尝试更改按钮的类或 id，那些类/id 的 CSS 将更改按钮的背景颜色。

**例 1:** 在本例中，类从**红色变为绿色。**

```tshtml
<!DOCTYPE HTML>
<html>

<head>
    <script src=
"//ajax.googleapis.com/ajax/libs/angularjs/1.2.13/angular.min.js">
    </script>

    <script>
        var myApp = angular.module("app", []);
        myApp.controller("controller", function ($scope) {
            $scope.myButton = 'red';
            $scope.changeCol = function () {
                $scope.myButton = "green";
            };
        });
    </script>
    <style type="text/css">
        .red {
            background: red;
            color: white;
        }

        .green {
            background: green;
            color: white;
        }
    </style>
</head>

<body style="text-align:center;">
    <h1 style="color:green;">
        GeeksForGeeks
    </h1>
    <p>
        How to change the color
        of the button in AngularJS
    </p>
    <div ng-app="app">
        <div ng-controller="controller">
            <button ng-click="changeCol()" 
                class="{{myButton}}">
                Click to change
            </button>
        </div>
    </div>
</body>

</html> 
```

**输出:**

![](img/a7f847f97bb9dba85aceac1c8a5d4c57.png)

**例 2:** 在本例中，按钮的 ID 由**蓝色变为绿色**。

```tshtml
<!DOCTYPE HTML>
<html>

<head>
    <script src=
"//ajax.googleapis.com/ajax/libs/angularjs/1.2.13/angular.min.js">
    </script>

    <script>
        var myApp = angular.module("app", []);
        myApp.controller("controller", function ($scope) {
            $scope.ID = 'blue';
            $scope.changeCol = function () {
                $scope.ID = "green";
            };
        });
    </script>

    <style type="text/css">
        #blue {
            background: blue;
            color: white;
        }

        #green {
            background: green;
            color: white;
        }
    </style>
</head>

<body style="text-align:center;">
    <h1 style="color:green;">
        GeeksForGeeks
    </h1>
    <p>
        How to change the color of
        the button in AngularJS
    </p>
    <div ng-app="app">
        <div ng-controller="controller">
            <button ng-click="changeCol()" 
                id="{{ID}}">
                Click to change</button>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/f428640a5d3480dd669a77900993d036.png)