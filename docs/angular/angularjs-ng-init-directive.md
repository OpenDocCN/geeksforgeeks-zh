# angolajs | ng-init 指令

> 原文:[https://www.geeksforgeeks.org/angularjs-ng-init-directive/](https://www.geeksforgeeks.org/angularjs-ng-init-directive/)

ng-init 指令用于初始化 AngularJS 应用程序数据。它为 AngularJS 应用程序定义初始值，并为变量赋值。
ng-init 指令定义了 AngularJS 应用程序的初始值和变量。

**语法:**

```ts
<element ng-init = "expression">
   ...
</element>

```

**示例:**在本例中，我们初始化一个字符串数组。

```ts
<html>
    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/
    angular.min.js"></script>
    <head>
        <title>AngularJS ng-init Directive</title>
    </head>
    <body>
            <h1 style = "color:green">GeeksforGeeks
            <h2>ng-init directive</h2>
            <div ng-app="" ng-init="sort=['quick sort', 'merge sort',
             'bubble sort']">
             Sorting techniques:
            <ul>
            <li>{{ sort[0] }} </li>
            <li>{{ sort[1] }} </li>
            <li>{{ sort[2] }} </li>
            </ul>
         </div>
    </body>
</html>
```

**输出:**
![ng-app](img/c27e5b19f1df4e9520e7c90da423d39e.png)