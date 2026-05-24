# AngularJS | ng-keypress 指令

> 哎哎哎:# t0]https://www . geeksforgeeks . org/angolajs-ng-key press-directive/

AngularJS 中的 `ng-keypress` 指令用于对按键事件应用自定义行为。支持 `<input>`、`<select>` 和 `<textarea>` 元素。

## 语法

```ts
<element ng-keypress="expression"> Contents... </element>
```

其中 `expression` 告诉按键时要做什么。

## 示例

本示例使用 `ng-keypress` 指令显示键值。

```ts
<!DOCTYPE html>
<html>

<head>
    <title>ng-keypress Directive</title>

<script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js">
    </script>

<script type="text/javascript">
        var app = angular.module('app', []);
        app.controller('geek', function ($scope) {
            $scope.getkeys = function (event) {
                $scope.keyval = event.keyCode;
            }
        });
    </script>
</head>

<body style="text-align:center">
    <div ng-app="app" ng-controller="geek">
        <h1 style="color:green">
            GeeksforGeeks
        </h1>

<h2>ng-keypress Directive</h2>

Enter Text: <input type="text"
                ng-keypress="getkeys($event)" >

<br><br>

<span style="color:Red">
            Key Code: {{keyval}}
        </span>
    </div>
</body>

</html>
```

## 输出

![ngkeypress](img/5771e35db17dd0aa2170b9eb0074e2da.png)