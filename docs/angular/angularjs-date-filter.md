# AngularJS |日期过滤器

> 原文:[https://www.geeksforgeeks.org/angularjs-date-filter/](https://www.geeksforgeeks.org/angularjs-date-filter/)

AngularJS 日期过滤器用于将日期转换为指定的格式。未指定日期格式时，默认日期格式为“MMM d，yyyy”。
**语法:**

```ts
{{ date | date : format : timezone }}
```

**参数值:**日期过滤器包含可选的格式和时区参数。
**格式中常用的一些值如下:**

*   ‘YYYY’–定义年份 ex。2019
*   “YY”——定义年份 ex。19
*   y’–定义年份 ex。2019
*   “MMMM”——定义月份 ex。四月
*   ‘MMM’–定义月份 ex。四月
*   ‘MM’–定义月份 ex。04
*   DD’–定义 ex 日。09
*   d’–定义 ex 日。9
*   hh’–以上午/下午定义小时
*   h’–以上午/下午定义小时
*   ‘mm’–定义分钟
*   m’–定义分钟
*   ‘ss’–定义第二个
*   s’–定义第二个

**格式的一些预定义值如下:**

*   “短”——相当于“M/d/yy h:mm a”
*   “中”–相当于“MMM d，y h:mm:ss a”
*   “短日期”——相当于“年月日”(19 年 7 月 5 日)
*   “中间日期”——相当于“2019 年 5 月 7 日”
*   “long date”——相当于“MMMM d，y”(2019 年 5 月 7 日)
*   “完整日期”——相当于“纽约州 MMMM 市 EEEE”(2019 年 5 月 7 日星期二)
*   “短时间”——相当于“小时:分钟”(凌晨 2:35)
*   “中间时间”——相当于“小时:分:秒”(凌晨 2:35:05)

**示例 1:** 本示例以给定的格式显示日期。

## 超文本标记语言

```ts
<!DOCTYPE html>
<html>
    <head>
        <title>Date Filter</title>

        <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js">
        </script>
    </head>

    <body>

        <div ng-app="gfgApp" ng-controller="dateCntrl">

<p>{{ today | date : "dd.MM.y" }}</p>

        </div>

        <script>
            var app = angular.module('gfgApp', []);
            app.controller('dateCntrl', function($scope) {
                $scope.today = new Date();
            });
        </script>
    </body>
</html>
```

**输出:**

```ts
07.05.2019
```

**示例 2:** 本示例以指定格式显示时间。

## 超文本标记语言

```ts
<!DOCTYPE html>
<html>
    <head>
        <title>Date Filter</title>

        <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js">
        </script>
    </head>

    <body>

        <div ng-app="gfgApp" ng-controller="dateCntrl">

<p>{{ today| date : 'mediumTime'}}</p>

        </div>

        <script>
            var app = angular.module('gfgApp', []);
            app.controller('dateCntrl', function($scope) {
                $scope.today = new Date();
            });
        </script>
    </body>
</html>
```

**输出:**

```ts
2:37:23 AM
```

**示例 3:** 本示例以指定的格式显示日期。

## 超文本标记语言

```ts
<!DOCTYPE html>
<html>
    <head>
        <title>Date Filter</title>

        <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js">
        </script>
    </head>

    <body>

        <div ng-app="gfgApp" ng-controller="dateCntrl">

<p>{{ today| date }}</p>

        </div>

        <script>
            var app = angular.module('gfgApp', []);
            app.controller('dateCntrl', function($scope) {
                $scope.today = new Date();
            });
        </script>
    </body>
</html>
```

**输出:**

```ts
May 7, 2019
```