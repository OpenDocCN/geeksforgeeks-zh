# Angular10 NgPluralCase 指令

> 原文: [https://www.geeksforgeeks.org/angular10-ngpluralcase-directive/](https://www.geeksforgeeks.org/angular10-ngpluralcase-directive/)

在本文中，我们将看到 Angular 10 中的 `NgPluralCase` 是什么，以及如何使用它。

Angular 10 中的 `NgPluralCase` 用于创建一个视图，当给定表达式与复数表达式匹配时，该视图将从父 `NgPlural` 中添加或删除。我们可以根据条件使用这些值使输出为复数或单数。

**语法:**

```ts
<li *NgPluralCase='condition'></li>
```

**`ngplural case` 使用的模块:** 模块为:

*   `通用模块`

**选择器:**

*   `【瓶颈期】`

**方法:**

*   创建 Angular 应用以使用。
*   使用 `NgPluralCase` 不需要导入。
*   在 `app.component.ts` 中。
*   在其中定义一个变量，并在需要检查条件的元素中使用 `ngPlural` 和 `ngPluralCase` 指令。
*   使用 `ng serve` 查看输出的 Angular 应用。

**例 1:**

## `app.component.ts`

```ts
import { Component } from '@angular/core';
@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
export class AppComponent {
    val = 1;
}
```

## `app.component.html`

```ts
<some-element [ngPlural]="val">
    <ng-template ngPluralCase="=1">Geek</ng-template>
    <ng-template ngPluralCase="=2">Geeks</ng-template>
</some-element>
```

**输出:**

```ts
Geek
```

**例 2:**

## `app.component.ts`

```ts
import { Component } from '@angular/core';
@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
export class AppComponent {
    valcar = 5;
}
```

## `app.component.html`

```ts
<some-element [ngPlural]="valcar">
    <ng-template ngPluralCase="=1">{{valcar}} Car</ng-template>
    <ng-template ngPluralCase="=5">{{valcar}} Cars</ng-template>
</some-element>
```

**输出:**

```ts
5 Cars
```

**参考:** [https://angular.io/api/common/NgPluralCase](https://angular.io/api/common/NgPluralCase)