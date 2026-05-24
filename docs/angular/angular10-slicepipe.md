# Angular10 SlicePipe

> 原文:[https://www.geeksforgeeks.org/angular10-slicepipe/](https://www.geeksforgeeks.org/angular10-slicepipe/)

在本文中，我们将看到什么是 Angular 10 中的**slicepie**以及如何使用它。

SlicePipe 用于创建包含元素切片的数组。

**语法:**

```ts
{{ value | SlicePipe }}
```

**模块:**slicepie 使用的模块是:

*   **General module**

**进场:**

*   创建要使用的角度应用程序
*   不需要任何导入就可以使用 SlicePipe
*   在 app.component.ts 中，定义采用 SlicePipe 值的变量。
*   在 app.component.html，使用上面带有“|”符号的语法来制作 SlicePipe 元素。
*   使用 ng serve 为 angular app 服务，以查看输出

**输入值:**

*   **Value:** It takes a string value.

**参数:**

*   **Start:** It takes a numerical value.
*   **end:** It takes a numerical value.

**例 1:**

 <gfg-tab role="tab" slot="tab" id="gfg-tab-0"><gfg-panel role="tabpanel" slot="panel" id="gfg-panel-0" data-code-lang="javascript">```ts
import { Component } from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html'
})
export class AppComponent {
    collection: string[] = ['geeks', 'for', 'geeks', 'gfg'];
  }
```</gfg-panel></gfg-tab>