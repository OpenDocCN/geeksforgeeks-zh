# 角度 ngx 引导报警组件

> 原文:[https://www . geesforgeks . org/angular-ngx-bootstrap-alerts-component/](https://www.geeksforgeeks.org/angular-ngx-bootstrap-alerts-component/)

Angular ngx bootstrap 是一个 bootstrap 框架，与 Angular 一起使用，创建具有很好风格的组件，这个框架非常容易使用，用于制作响应性网站。

在本文中，我们将了解如何在 angular ngx 引导中使用 alert。**提醒**用于为少数可用的典型用户操作提供上下文反馈消息。

**安装语法:**

```ts
npm install ngx-bootstrap --save
```

**进场:**

*   First, install the angular ngx bootstrap using the above-mentioned command.

*   在 index.html

    > <link href="”https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css”" rel="”stylesheet”">

    添加以下脚本
*   在模块中导入警报组件
*   在 app.component.html 做一个警戒组件。
*   使用 ng serve 为应用提供服务。

**例 1:**

## index.html

```ts
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <base href="/">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">
    <link href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
        rel="stylesheet">

    <link rel="icon" type="image/x-icon" 
                    href="favicon.ico">
    <link rel="preconnect" 
        href="https://fonts.gstatic.com">
    <link href=
"https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&display=swap"
        rel="stylesheet">
    <link href=
        "https://fonts.googleapis.com/icon?family=Material+Icons" 
        rel="stylesheet">
</head>

<body class="mat-typography">
    <app-root></app-root>
</body>

</html>
```

## app.component.html

```ts
<alert type="secondary">
    <strong>GeeksForGeeks</strong> Alert no-1
</alert>
<alert type="danger">
    <strong>GeeksForGeeks</strong> Alert no-2
</alert>
<alert type="primary">
    <strong>GeeksForGeeks</strong> Alert no-3
</alert>
<alert type="warning">
    <strong>GeeksForGeeks</strong> Alert no-4
</alert>
```

## app.module.ts

```ts
import { NgModule } from '@angular/core';

// Importing forms module
import { FormsModule, ReactiveFormsModule }
    from '@angular/forms';
import { BrowserModule }
    from '@angular/platform-browser';
import { BrowserAnimationsModule }
    from '@angular/platform-browser/animations';
import { AlertModule }
    from 'ngx-bootstrap/alert';

import { AppComponent }
    from './app.component';

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
        AlertModule.forRoot()

    ]
})
export class AppModule { }
```

**输出:**

![](img/bb3ffaabdcb8007c0a3e0b2ba0fef0d1.png)

**参考:**T2】https://valor-software.com/ngx-bootstrap/#/alerts