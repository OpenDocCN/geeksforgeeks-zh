# Angular10 SlicePipe

> 原文:[https://www.geeksforgeeks.org/angular10-slicepipe/](https://www.geeksforgeeks.org/angular10-slicepipe/)

在本文中，我们将看到什么是 Angular 10 中的`SlicePipe`以及如何使用它。

`SlicePipe`用于创建包含元素切片的数组。

## 语法

```ts
{{ value | SlicePipe }}
```

## 模块

`SlicePipe`使用的模块是:

*   `CommonModule`

## 进场

*   创建要使用的 Angular 应用程序。
*   不需要任何导入就可以使用`SlicePipe`。
*   在`app.component.ts`中，定义采用`SlicePipe`值的变量。
*   在`app.component.html`，使用上面带有“|”符号的语法来制作`SlicePipe`元素。
*   使用`ng serve`为 Angular app 服务，以查看输出。

## 输入值

*   **Value:** It takes a string value.

## 参数

*   **Start:** It takes a numerical value.
*   **end:** It takes a numerical value.

## 例 1

```ts
import { Component } from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html'
})
export class AppComponent {
    collection: string[] = ['geeks', 'for', 'geeks', 'gfg'];
}
```