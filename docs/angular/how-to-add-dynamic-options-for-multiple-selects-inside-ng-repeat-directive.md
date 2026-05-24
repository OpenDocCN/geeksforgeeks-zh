# 如何在 ng-repeat 指令中添加多重选择的动态选项？

> 原文:[https://www . geesforgeks . org/如何添加-动态-选项-多重选择-内部-ng-重复-指令/](https://www.geeksforgeeks.org/how-to-add-dynamic-options-for-multiple-selects-inside-ng-repeat-directive/)

给定一个包含一些选项元素的 HTML 文档，任务是使用 angularJS 中的 ng-repeat 动态添加一个带有多个选择的 javascript 对象数组。

**方法:**使用 ng-repeat 完成任务，ng-repeat 在数组中循环。这个阵**就叫【模型】**吧。DOM 中的每个选择菜单都被建模为数组中的特定索引。例如，第二个<sup>第二个</sup>选择菜单将被建模为模型对象数组中的第二个<sup>第三个</sup>对象。为了给 DOM 添加更多的选择菜单，我们只需要将一个空对象推送到模型的数组中，ng-repeat 指令负责其余的复制。

**示例 1:** 在本例中，我们将添加多个选择并显示所选数据。

```ts
<!DOCTYPE html>
<html ng-app="gfg">

<head>
    <meta charset="utf-8" />
    <script data-require="angular.js@1.5.x"
            src=
"https://cdnjs.cloudflare.com/ajax/libs/angular.js/1.5.11/angular.min.js"
            data-semver="1.5.11">
    </script>

    <script>
        var app = angular.module('gfg', []);

        app.controller('MainCtrl', function($scope) {
            $scope.models = [{}];
            $scope.countries = ['India', 'Japan', 'US'];
            $scope.states = {
                India: ['UP', 'MP', 'Bihar'],
                Japan: ['Tokyo', 'Yokohama'],
                US: ['California', 'Texas'],
            }
            $scope.addRow = function() {
                $scope.models.push({});
            }
            $scope.getState = function(country) {
                return $scope.states[country];
            }
        });
    </script>
</head>

<body ng-controller="MainCtrl">
    <center>
        <h1 style="color: green;">
            GeeksForGeeks
        </h1>

        <table>
            <tr>
                <th>Country</th>
                <th>State</th>
                <th>Action</th>
            </tr>

            <tr ng-repeat="model in models">
                <td>
                    <select ng-options=
                    "country as country for country in countries"
                            ng-model="model.country"
                            ng-change='getState(model.country)'>
                    </select>
                </td>
                <td>
                    <select ng-options=
            "state as state for state in getState(model.country)"
                            ng-model="model.state">
                    </select>
                </td>
                <td>
                    <button ng-click="addRow()">Add Row</button>
                </td>
            </tr>
        </table>
        <h3 style="color:green">Selections</h3>
        <p ng-repeat="model in models">
            {{model.country}} - {{model.state}}
        </p>
    </center>
</body>

</html>
```

**输出:**所有数据成功添加到对象数组。
T3】

**示例 2:** 在本例中，我们预填充了模型数组。

```ts
<!DOCTYPE html>
<html ng-app="gfg">

<head>
    <meta charset="utf-8" />
    <script data-require="angular.js@1.5.x"
            src=
"https://cdnjs.cloudflare.com/ajax/libs/angular.js/1.5.11/angular.min.js"
            data-semver="1.5.11">
    </script>

    <script>
        var app = angular.module('gfg', []);

        // Prepopulate the models array here
        app.controller('MainCtrl', function($scope) {
            $scope.models = [{
                country: 'India',
                state: 'UP'
            }];
            $scope.countries = ['India', 'Japan', 'US'];
            $scope.states = {
                India: ['UP', 'MP', 'Bihar'],
                Japan: ['Tokyo', 'Yokohama'],
                US: ['California', 'Texas'],
            }
            $scope.addRow = function() {
                $scope.models.push({});
            }
            $scope.getState = function(country) {
                return $scope.states[country];
            }
        });
    </script>
</head>

<body ng-controller="MainCtrl">
    <center>
        <h1 style="color: green;">
            GeeksForGeeks
        </h1>

        <table>
            <tr>
                <th>Country</th>
                <th>State</th>
                <th>Action</th>
            </tr>

            <tr ng-repeat="model in models">
                <td>
                    <select ng-options=
            "country as country for country in countries"
                        ng-model="model.country"
                        ng-change='getState(model.country)'>
                    </select>
                </td>
                <td>
                    <select ng-options=
         "state as state for state in getState(model.country)"
                            ng-model="model.state">
                    </select>
                </td>
                <td>
                    <button ng-click="addRow()">Add Row</button>
                </td>
            </tr>
        </table>
        <h3 style="color:green">Selections</h3>
        <p ng-repeat="model in models">
            {{model.country}} - {{model.state}}
        </p>
    </center>
</body>

</html>
```

**输出:**我们看到页面现在总是包含国家“印度”和状态“UP”作为页面加载时的预填充。
T3】