# 角度 10%管道

> 原文:[https://www.geeksforgeeks.org/angular10-percentpipe/](https://www.geeksforgeeks.org/angular10-percentpipe/)

在本文中，我们将看到什么是 Angular 10 中的 **percentPipe** 以及如何使用它。

百分比管道用于将数字转换为百分比字符串。

**语法:**

```ts
{{ value | percent [ : digitsInfo [ : locale ] ] }}
```

**模块:**百分比管道使用的模块是:

**进场:**

*   创建要使用的角度应用程序
*   使用百分比管道不需要任何导入
*   在 app.component.ts 中，定义采用 percentPipe 值的变量。
*   在 app.component.html，使用上面带有“|”符号的语法来构成 percentPipe 元素。
*   使用 ng serve 为 angular app 服务，以查看输出

**输入值:**

*   **Value:** It takes a string value.

**参数:**

*   [T0】 digitinfo: 【T1] It takes a string value.
*   **locale:** It takes a string value.

**例 1:**

 <gfg-tab role="tab" slot="tab" id="gfg-tab-0"><gfg-panel role="tabpanel" slot="panel" id="gfg-panel-0" data-code-lang="javascript">```ts
import { Component, OnInit } from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html'
})
export class AppComponent {
    geeks: number = 0.4945;
    gfg: number = 2.343564;
  }
```</gfg-panel></gfg-tab>