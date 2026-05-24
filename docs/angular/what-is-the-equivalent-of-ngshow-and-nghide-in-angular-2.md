# Angular 2+中 ngShow 和 ngHide 的等价量是多少？

> 原文:[https://www . geeksforgeeks . org/angular-2 中的等效物是什么/](https://www.geeksforgeeks.org/what-is-the-equivalent-of-ngshow-and-nghide-in-angular-2/)

**ngShow** 和 **ngHide** 是 AngularJS 中的两个 ng 指令，分别用于显示和隐藏元素。ngShow 用于通过将 div 选项卡链接到脚本中的布尔变量来显示该选项卡。如果变量值为真，则显示该项，否则该项保持隐藏，反之亦然。

**ng-show 示例:**该示例演示了 ngShow 的工作原理。

```ts
<html>
<script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js">
</script>

<body ng-app="">
    <div ng-show="true">
        <h1 style="color:green;">GeeksForGeeks</h1>
    </div>
</body>

</html>
```

**输出:**
![](img/f8f6abf6f327924814c06b68f1bb08f5.png)
同样，如果 ng-show 值设置为 false，那么它将消失。

**ng-hide 示例:**该示例演示了 nghide 的工作原理。

```ts
<html>
<script src=
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js">
</script>

<body ng-app="">
    <div ng-hide="true">
        <h1 style="color:green;">
          GeeksForGeeks
      </h1>
    </div>
</body>

</html>
```

**输出:**这里的输出是黑屏，因为 ng-hide 设置为 true，这意味着 GeeksForGeeks 是隐藏的。类似地，如果真被更改为假，则显示如下:
![](img/f8f6abf6f327924814c06b68f1bb08f5.png)

**在 Angular 2+**
上实现在 Angular 中，有两种方式实现 ng-hide 和 ng-show:

1.  **By using <q>[hidden]</q> property:**<q>[hidden]</q> property in angular, modifies the display property and does no change with the DOM. It only instructs the browser to not show the content

    **语法:**

    ```ts
    <div [hidden]="boolean_var"></div>
    ```

    因为它不会对 DOM 造成任何阻碍，所以如果在 CSS 中使用显示属性，那么这将会失败。例如，对于上面的示例，如果按如下方式操作，[隐藏]将会失败。

    ```ts
    <div [hidden]="boolean_var" style="display:block; ></div>
    ```

    隐藏属性的 RHS 端由组件类中的布尔变量的名称组成。该变量的值决定了<q>【隐藏】</q>是否隐藏。

    **示例:**

    *   **模板文件**

        ```ts
        <div [hidden]="isHidden">
            This will be hidden..
        </div>
        ```

    *   **组件类**

        ```ts
        import {
            Component,
            OnInit
        }

        from '@angular/core';
        @Component( {
            selector: 'app-list', templateUrl: 
              './list.component.html', styleUrls:
              ['./list.component.css']
        }

        ) export class ListComponent implements OnInit {
            isHidden: boolean=true;
            constructor() {}
            ngOnInit() {}
        }
        ```

    *   **输出:**这不会在屏幕上显示任何内容。
2.  **By using <q>*ngIf</q> directive:** It is a more effective way that [hidden]. It effectively removes the content from the DOM and thus there are loopholes in this method.

    **语法:**

    ```ts
    <div *ngIf="boolean_var"></div>
    ```

    类似于[隐藏]属性，该属性的 RHS 端由组件类中的布尔变量的名称组成。该变量的值决定了内容是否在 DOM 中。

    **示例:**

    *   **模板文件**

        ```ts
        <div *ngIf="isShown">
            This will be Shown..
        </div>
        ```

    *   **组件类:**

        ```ts
        import { Component, OnInit } from '@angular/core';

        @Component({
          selector: 'app-list',
          templateUrl: './list.component.html',
          styleUrls: ['./list.component.css']
        })
        export class ListComponent implements OnInit {

        isShown:boolean=true;
          constructor() { }

          ngOnInit() {
          }
        }
        ```

    *   **输出:**

        ```ts
        This will be Shown..
        ```