# Angular 10 NgSwitchCase 指令

> 原文: [https://www.geeksforgeeks.org/angular10-ngswitchcase-directive/](https://www.geeksforgeeks.org/angular10-ngswitchcase-directive/)

在本文中，我们将了解 Angular 10 中的 `NgSwitchCase` 是什么以及如何使用它。

Angular 10 中的 `NgSwitchCase` 用于创建一个视图，当给定的表达式与父 `ngSwitch` 表达式的值匹配时，该视图将被添加或从 DOM 中移除。

**语法:**

```ts
<li *ngSwitchCase="'condition'"></li>
```

## NgSwitchCase 使用的模块

模块为:

*   `CommonModule`

## 选择器

*   `*ngSwitchCase`

## 方法

*   创建一个要使用的 Angular 应用程序。
*   不需要任何导入就可以使用 `NgSwitchCase`。
*   在 `app.component.ts` 中定义一个变量。
*   在 `app.component.html` 中，在需要检查条件的元素中使用带有 `NgSwitchCase` 指令的 `ngSwitch`。
*   使用 `ng serve` 为 Angular 应用提供服务，以查看输出。

## 例 1

### app.component.ts

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  num = 2;
}
```

### app.component.html

```ts
<div [ngSwitch]="num">
  <div *ngSwitchCase="'1'">One</div>
  <div *ngSwitchCase="'2'">Two</div>
  <div *ngSwitchCase="'3'">Three</div>
  <div *ngSwitchCase="'4'">Four</div>
  <div *ngSwitchCase="'5'">Five</div>
</div>
```

**输出:**

![](img/146db0aeca1e390c9f38b8c589b21516.png)

**参考:** [https://angular.io/api/common/NgSwitchCase](https://angular.io/api/common/NgSwitchCase)