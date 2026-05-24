# 角度 10(焦点)事件

> 原文:[https://www.geeksforgeeks.org/angular-10-focus-event/](https://www.geeksforgeeks.org/angular-10-focus-event/)

在本文中，我们将看到什么是 Angular 10 中的焦点事件以及如何使用它。当元素获得焦点时，会触发(焦点)事件。

**语法:**

```ts
<input (focus)='functionName()'/>
```

**模块:**焦点事件使用的模块是:

*   **公共模块**

**进场:**

*   创建一个要使用的角度应用程序。
*   在 app.component.ts 中，创建一个在焦点事件上触发的函数。
*   在 app.component.html，制作一个输入元素并设置焦点事件。
*   使用 ng serve 为 angular app 服务，以查看输出。

**例 1:**

## app.component.ts

```ts
import { Component } from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})

export class AppComponent {
    onFocus(): void {
        console.log('Focus Is gained for this Element');
    }
}
```

## app.component.html

```ts
<br>
<form>
    <input placeholder="Name" (focus) = 'onFocus()'>
</form>
```

**输出:**

![](img/20d97df58d73be03e5785a92c8104f4d.png)

**例 2:**

## app.component.ts

```ts
import { Component } from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})

export class AppComponent {
    onFocus(): void {
        console.log('Focus Is gained for this Element');
    }
}
```

## app.component.html

```ts
<br>
<form>
    <button (focus) = 'onFocus()'>Click here!</button>
</form>
```

**输出:**

![](img/088b236862633094b7af2249dd6cb825.png)