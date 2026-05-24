# 如何使用 AngularJS 更改日期格式？

> 原文:[https://www . geesforgeks . org/how-to-change-date-format-use-angularjs/](https://www.geeksforgeeks.org/how-to-change-the-date-format-using-angularjs/)

AngularJS 提供了两种不同的方法来更改日期的格式。这可以通过以下方法实现:

*   使用超文本标记语言模板绑定
*   使用 JavaScript

**HTML 模板绑定:**在这个方法中，我们使用了 pipe (|)运算符。该管道操作符有助于根据所需格式(包括角度标准格式和用户定义格式)转换日期对象、数字。在 angular 中，可以使用此运算符基于任何格式、区域设置和时区修改日期对象。它只以可读的格式格式化日期。

**语法:**

```tshtml
{{ dateVariable | date [ : format [ : timezone [ : locale ] ] ] }}
```

**属性描述:**

| 属性 | 描述 |
| 格式 | 预定义和用户定义的格式都可以用在这个属性中。此参数的默认值为–“中间日期”。**可选参数** |
| 时区 | 时区的默认值是–用户的本地系统时区。我们可以提供偏移值(' 0530 ')或标准世界协调时/格林尼治标准时(IST)或美国大陆时区缩写。**可选参数** |
| 现场 | 区域设置的默认值是–“未定义”。例如，我们可以将其设置为–‘en _ US’。**可选参数** |

**示例:**在本例中，我们将当前日期更改为不同的格式。该日期格式包括标准格式和用户定义的格式。

```tshtml
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js">
    </script>
</head>

<body>
    <div ng-app="myApp" ng-controller="datCtrl">
        <p>
            Formatted Date with default parameters:
            {{ dateValue | date }}
        </p>

        <p>
            Formatted Date with standard filter (ShortDate):
            {{ dateValue | date:'shortDate' }}
        </p>

        <p>
            Formatted Date with standard filter (FullDate):
            {{ dateValue | date:'fullDate' }}
        </p>

        <p>
            Formatted date with user defined format:
            {{ dateValue | date : "'today is ' MMMM d, y" }}
        </p>
    </div>

    <script>
        var app = angular.module('myApp', []);
        app.controller('datCtrl', function ($scope) {
            $scope.dateValue = new Date();
        });
    </script>
</body>

</html>
```

当我们运行代码时，它会以不同的格式提供当前日期。

```tshtml
Input Current Date: 24th March 2020
```

**输出:**

```tshtml
Formatted Date with default parameters: Mar 24, 2020 
Formatted Date with standard filter (ShortDate): 3/24/20
Formatted Date with standard filter (FullDate): Tuesday, March 24, 2020
Formatted date with user defined format:today is March 24, 2020

```

正如我们已经看到的，使用这个管道操作器非常容易。现在我们来看看第二种方法。

**使用 JavaScript 控制器:**如果您有字符串格式的日期，这种方法会很有帮助。

**Syntax:**

```tshtml
$scope.dateVariable = $filter('date')("dateString", "dateformat");
```

**示例:**这里，我们使用角度控制器来更改日期格式。日期作为字符串并通过使用$filter filter 传递，该筛选器用于筛选对象元素和数组。它以指定的格式为您提供原始数组的子集。

```tshtml
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js">
    </script>

    <title>
        How to change the date format using AngularJS ?
    </title>
</head>

<body>
    <div ng-app="MyApp">
        <div ng-controller="MyCtrl">
            Input Date in String Format: {{myDate}}<br>
            Output Date : {{myDateFiltered}}
        </div>
    </div>

    <script>
        var app = angular.module('MyApp', []);

        app.controller('MyCtrl', ['$scope', '$filter', 
                function ($scope, $filter) {
            $scope.myDate = new Date('2013/07/21');

            $scope.myDateFiltered = $filter('date')
                    ($scope.myDate, 'dd/MM/yy');
        }]);
    </script>
</body>

</html>
```

**输出:**

```tshtml
Input Date in String Format: "2013-07-20T18:30:00.000Z"
Output Date : 21/07/13

```