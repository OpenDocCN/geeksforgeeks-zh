# 在 Angular 9 中更改日期时，如何刷新整个应用程序？

> 原文：[https://www.geeksforgeeks.org/how-to-refresh-entire-application-when-date-is-changed-in-angular-9/](https://www.geeksforgeeks.org/how-to-refresh-entire-application-when-date-is-changed-in-angular-9/)

在这个例子中，我们将看到如何在 AngularJS 中更新日期。

## 方法

*   首先，我们需要在 `HTML` 文件中编写代码来显示日期选择器。
*   我们可以通过将 `input` 的 `type` 设置为 `date` 来实现。
*   设置类型后，我们需要在 `onchange` 事件上声明一个函数，这样每当日期改变时，应用程序就会重新加载。
*   在 `HTML` 文件中声明函数后，我们需要在 `ts` 文件中编写函数实现。
*   在函数实现中，我们可以使用 `DOM` 的 `window` 属性，并调用 `reload` 函数来重新加载应用程序。
*   完成上述步骤后，服务或启动项目。

## 代码实现

### `app.component.ts`

```ts
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
export class AppComponent {
    constructor() { }

    // Function to reload the application
    refreshPage() {
        window.location.reload();
    }
}
```