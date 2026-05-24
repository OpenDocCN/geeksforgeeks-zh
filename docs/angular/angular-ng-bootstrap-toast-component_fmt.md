# Angular ng-bootstrap Toast 组件

> 原文：[https://www.geeksforgeeks.org/angular-ng-bootstrap-toast-component/](https://www.geeksforgeeks.org/angular-ng-bootstrap-toast-component/)

Angular ng-bootstrap 是一个 Bootstrap 框架，与 Angular 一起使用来创建具有很好风格的组件。这个框架非常容易使用，用于制作响应性网站。
在本文中，我们将看到如何在 Angular ng-bootstrap 中使用 Toast。Toast 组件用于制作向用户提供反馈消息的组件。

## 安装语法

```
ng add @ng-bootstrap/ng-bootstrap
```

## 步骤

1.  首先，使用上述命令安装 `@ng-bootstrap/ng-bootstrap`。
2.  在 `index.html` 文件中添加以下样式表链接：
    ```
    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" rel="stylesheet">
    ```
3.  在模块中导入 `NgbModule`：
    ```ts
    import { NgbModule } from '@ng-bootstrap/ng-bootstrap';
    imports: [
        NgbModule
    ]
    ```
4.  在 `app.component.html` 文件中创建一个 Toast 组件。
5.  使用 `ng serve` 为应用提供服务。

## 示例 1

在这个示例中，我们正在制作 Toast 的基本示例。

### app.component.html

```ts
<ngb-toast [autohide]="false" id='gfg'>
    GeeksforGeeks Angular ng bootstrap
</ngb-toast>
```

### app.module.ts

```ts
import { NgModule } from '@angular/core';

// Importing forms module
import { FormsModule, ReactiveFormsModule }
from '@angular/forms';
import { BrowserModule }
from '@angular/platform-browser';
import { BrowserAnimationsModule }
from '@angular/platform-browser/animations';

import { AppComponent } from './app.component';
import { NgbModule }
from '@ng-bootstrap/ng-bootstrap';

@NgModule({
  bootstrap: [
    AppComponent
  ],
  declarations: [
    AppComponent
  ],
  imports: [
    FormsModule,
    BrowserModule,
    BrowserAnimationsModule,
    ReactiveFormsModule,
    NgbModule
  ]
})
export class AppModule { }
```

### app.component.css

```ts
#gfg {
    margin:40px
}
```

### 输出

![](img/98811395beecdfc9335e85b9725bca57.png)

## 示例 2

在这个例子中，我们正在用 header 制作 Toast。

### app.component.html

```ts
<ngb-toast [autohide]="false" id='gfg' header='GeeksforGeeks'>
    Angular ng bootstrap
</ngb-toast>
```

### app.module.ts

```ts
import { NgModule } from '@angular/core';

// Importing forms module
import { FormsModule, ReactiveFormsModule }
from '@angular/forms';
import { BrowserModule }
from '@angular/platform-browser';
import { BrowserAnimationsModule }
from '@angular/platform-browser/animations';

import { AppComponent } from './app.component';
import { NgbModule }
from '@ng-bootstrap/ng-bootstrap';

@NgModule({
  bootstrap: [
    AppComponent
  ],
  declarations: [
    AppComponent
  ],
  imports: [
    FormsModule,
    BrowserModule,
    BrowserAnimationsModule,
    ReactiveFormsModule,
    NgbModule
  ]
})
export class AppModule { }
```

### app.component.css

```ts
#gfg {
    margin:40px
}
```

### 输出

![](img/1a918c0a87f640002e9db76ce3b57ed6.png)

## 参考

[https://ng-bootstrap.github.io/#/components/toast/overview](https://ng-bootstrap.github.io/#/components/toast/overview)