# 如何在 AngularJS 中选择对象中的第一个对象？

> 原文:[https://www . geeksforgeeks . org/如何选择-先物后物-in-object-in-angularjs/](https://www.geeksforgeeks.org/how-to-select-first-object-in-object-in-angularjs/)

我们正在处理的主要问题是，对于对象的对象，读取特定索引位置的对象并不像列表那么简单。我们不能用神经生长因子作为一个不被认为是**可迭代**的对象来循环它。当从任何来源接收的数据是包含对象的对象(如 JSON 文件)时，这个问题的重要性可能会出现。
修改源文件非常不方便，所以我们需要能够在应用程序本身做一些事情。最有效的办法就藏在问题本身。如果对象不可迭代，则将它们转换为可迭代。

下面讨论两种方法来解决这个问题。

*   **Approach 1:**
    *   使用 [ng-repeat](https://docs.angularjs.org/api/ng/directive/ngRepeat) 指令和 [limitTo](https://docs.angularjs.org/api/ng/filter/limitTo) 过滤器。
    *   ng-repeat 能够迭代对象的属性，在我们的例子中，对象本身就是对象。使用以下语法:

        ```ts
        < div ng-repeat="(key, value) in myObj" > ... < /div >
        ```

    *   限制筛选器创建只包含指定数量元素的新数组或字符串。元素取自源数组、字符串或数字的开头或结尾，由 limit 的值和符号(正或负)指定。

    **语法:**

    ```ts
    html binding:
    {{ limitTo_expression | limitTo : limit : begin}}

    ```

    **示例:**极限的值可以被改变以获得可迭代的元素(在这种情况下是对象)

    ```ts
    <!DOCTYPE html>
    <html>

    <head>
        <title>Angular first object in object</title>
        <script src=
    "https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js">
        </script>
    </head>

    <body ng-app='MyApp' 
          ng-controller='MyCtrl'>
        <div ng-repeat="(key, obj) in institute | limitTo : 1">
            <ul>
                <li ng-repeat="(prop, value) in obj">
                    {{prop}}: {{value}}
                </li>
            </ul>
        </div>
        <script>
            var app = angular.module('MyApp', []);
            app.controller('MyCtrl', function($scope) {
                $scope.institute = {
                    'school': {
                        location: 'Jamshedpur',
                        name: 'RV'
                    },
                    'college': {
                        location: 'Kolkata',
                        name: 'Jadavpur'
                    }
                };
                var instilist = new Array();
                for (key of Object.keys($scope.institute)) {
                    instilist.push($scope.institute[key]);
                }
                $scope.institute = instilist;
            });
        </script>
    </body>

    </html>
    ```

    **输出:**这是对象研究所的第一个对象的元素(在上面的代码中提到过)。
    T3】

*   **Approach 2:**
    *   将对象的对象转换为对象数组，并使用方括号([])的索引方法显示数组的第一个对象。

    **语法:**

    ```ts
    {{name_of_the array[index]}}
    ```

    **示例:**数组第一个对象的索引值为 0。因为数组的元素是对象，所以我们可以使用(。)运算符。

    ```ts
    <!DOCTYPE html>
    <html>

    <head>
        <title>Angular first object in object</title>
        <script src=
    "https://ajax.googleapis.com/ajax/libs/angularjs/1.3.14/angular.min.js">
        </script>
    </head>

    <body>
        <div ng-app="MyApp" ng-controller="MyCtrl">
            <p>The Name of the school is: {{institute[0].name}}</p>
        </div>

        <script>
            var app = angular.module('MyApp', []);
            app.controller('MyCtrl', function($scope) {
                $scope.institute = {
                    school: {
                        location: 'Jamshedpur',
                        name: 'RV'
                    },
                    college: {
                        location: 'Kolkata',
                        name: 'Jadavpur'
                    }
                };
                var instilist = new Array();
                for (key of Object.keys($scope.institute)) {
                    instilist.push($scope.institute[key]);
                }
                $scope.institute = instilist;
            });
        </script>
    </body>

    </html>
    ```

    **输出:**这显示了对象研究所的第一个对象的属性之一(在上面的代码中提到)。
    T3】