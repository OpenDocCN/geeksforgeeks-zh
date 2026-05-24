# Angular10 NgPluralCase 指令

> 原文:[https://www . geeksforgeeks . org/angular 10-ngpluralcase-指令/](https://www.geeksforgeeks.org/angular10-ngpluralcase-directive/)

在本文中，我们将看到 Angular 10 中的 NgPluralCase 是什么，以及如何使用它。

angular 10 中的 **NgPluralCase** 用于 c 创建一个视图，当给定表达式与复数表达式匹配时，该视图将从父 NgPlural 中添加或删除。我们可以根据条件使用这些值使输出为复数或单数。

**语法:**

```ts
<li *NgPluralCase='condition'></li>
```

**ngplural case 使用的模块:**模块为:

*   **通用模块**

**选择器:**

*   **【瓶颈期】**

**方法:**

*   Create Angular app to use.
*   No import is required to use NgPluralCase.
*   在 app.component.ts
*   Define a variable in, and use the ngPlural and ngPluralCase instructions in the elements that need to check the conditions.
*   Use ng serve to view the output angle app.

**例 1:**

## app . component . ts

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

## app.component.html

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

## app . component . ts

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

## app.component.html

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

**参考:**T2】https://angular.io/api/common/NgPluralCase