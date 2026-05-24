# 在 angular 9 中更改日期时，如何刷新整个应用程序？

> 原文:[https://www . geeksforgeeks . org/如何刷新整个应用程序-更改时间-角度-9/](https://www.geeksforgeeks.org/how-to-refresh-entire-application-when-date-is-changed-in-angular-9/)

在这个例子中，我们将看到如何在 angularJS 中更新日期。

**方法:**

*   First, we need to write the code to display the date selector in the HTML file.
*   We can do this by giving the input type as the date.
*   After entering the type, we need to declare a function on the' onchange' event, so that whenever the date changes or changes, the application will be reloaded.
*   After declaring the function in the HTML file, we need to write the function implementation in the ts file.
*   In the function implementation, we can use the window property of DOM, and we can call the reload function to reload the application.
*   After completing the above steps, service or start the project.

**代码实现:**

**app . component . ts:**

## Javascript

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