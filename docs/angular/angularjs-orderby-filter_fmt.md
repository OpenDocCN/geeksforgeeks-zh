# AngularJS | orderBy Filter

> 原文: [https://www.geeksforgeeks.org/angularjs-orderby-filter/](https://www.geeksforgeeks.org/angularjs-orderby-filter/)

``orderBy`` 过滤器是一个用于 AngularJS 的便捷工具。
``orderBy`` 过滤器鼓励您对数据进行排序。
它按照字母顺序对字符串进行排序，并按照数字顺序对数字进行排序。

## 语法

```ts
{{ orderBy_expression | orderBy : expression : reverse }}
```

## 参数说明

- **expression**: 用于决定排序的表达式。它很可能是一个字符串、函数或一个数组。
- **reverse**: 这是可选的。如果您希望数据以相反的顺序显示，请确保将参数中的 ``reverse`` 条件设置为 ``true``。

## 例子：按名称排序（区分大小写）

```ts
<!DOCTYPE html>
<html>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>
<div ng-app="myApp" ng-controller="orderCtrl">
<ul>
<li ng-repeat="x in customers | orderBy : 'name'">
    {{x.name + ", " + x.city}}
</li>
</ul>
</div>
<script>
var app = angular.module('myApp', []);
app.controller('orderCtrl', function($scope) {
    $scope.customers = [
        {"name" : "Amber", "city" : "ajmer"},
        {"name" : "lakshay ", "city" : "vizag"},
        {"name" : "karan", "city" : "London"},
        {"name" : "bhaskar", "city" : "peshawar"},
];
});
</script>
<p>The array items are arranged by "name".</p>
</body>
</html>
```

**输出:**

![output1](img/62836a8d789f5fc1c977bf7edc9fbafb.png)

## 例子：按 GDP 排序（使用 `-` 和 `+`）

```ts
<!DOCTYPE html>
<html>
<head>
  <title>AngularJS Filters : orderBy </title>
   <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js"></script>
  <style>
    .tabled{float:left; padding:10px;}
  </style>
 </head>
<body ng-app="orderByDemo">
 <script>
  angular.module('orderByDemo', [])
    .controller('orderByController', ['$scope', function($scope) {
      $scope.countries =
          [{name:'SPAIN', states:'78', gdp:5},
           {name:'FRANCE', states:'46', gdp:4},
           {name:'PORTUGAL', states:'53', gdp:3},
           {name:'CHILE', states:'06', gdp:2},
           {name:'RUSSIA', states:'21', gdp:1}];
    }]);
</script>
<div ng-controller="orderByController">

<table class="tabled">
    <tr>
      <th>Name</th>
      <th>No of States</th>
      <th>GDP(descending)</th>
    </tr>
    <!-- orderBy Descending (-) -->
    <tr ng-repeat="country in countries | orderBy:'-gdp'">
      <td>{{country.name}}</td>
      <td>{{country.states}}</td>
      <td>{{country.gdp}}</td>
    </tr>
  </table>

<table class="tabled">
    <tr>
      <th>Name</th>
      <th>No of States</th>
      <th>GDP(ascending)</th>
    </tr>
    <!-- orderBy Ascending (+) -->
    <tr ng-repeat="country in countries | orderBy:'gdp'">
      <td>{{country.name}}</td>
      <td>{{country.states}}</td>
      <td>{{country.gdp}}</td>
    </tr>
  </table>
</div>
</body>
</html>
```

**输出:**

![output example 2](img/7568fbd53554ec11d5442f273648f16b.png)

## 例子：按国家排序（七大奇迹）

```ts
<!DOCTYPE html>
<html>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js"></script>
<body>

<div ng-app="myApplication" ng-controller="orderCtrl">

<ul>
<li ng-repeat="x in sevenwonder | orderBy : '-country'">
{{x.name + ", " + x.country}}</li>
</ul>

</div>

<script>
var application = angular.module('myApplication', []);
application.controller('orderCtrl', function($scope) {
    $scope.sevenwonder = [
        {"name" : "Great Wall of China" ,"country" : "China"},
        {"name" : "Christ the Redeemer Statue", "country" : "Brazil"},
        {"name" : "Machu Picchu", "country" : "peru"},
        {"name" : "Chichen Itza ", "country" : "Mexico"},
        {"name" : "The Roman Colosseum", "country" : "Rome"},
        {"name" : "Taj Mahal", "country" : "India"},
        {"name" : "Petra", "country" : "Jordan"}
    ];
});
</script>
<p>The array items are sorted by "country".</p>

</body>
</html>
```

**输出:**

![](img/269e94e039f7ab4163ce7c6c005077e3.png)