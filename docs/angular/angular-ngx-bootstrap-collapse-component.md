# 角度 ngx 自举折叠组件

> 原文:[https://www . geesforgeks . org/angular-ngx-bootstrap-collapse-component/](https://www.geeksforgeeks.org/angular-ngx-bootstrap-collapse-component/)

Angular ngx bootstrap 是一个 bootstrap 框架，与 Angular 一起使用，创建具有很好风格的组件，这个框架非常容易使用，用于制作响应性网站。

在本文中，我们将学习如何在 angular ngx bootstrap 中使用折叠。**折叠**用于制作一个按钮，点击该按钮即可折叠。

**安装语法:**

```ts
npm install ngx-bootstrap --save
```

**进场:**

*   首先，使用上述命令安装 angular ngx 引导程序。
*   在 index.html

    > <link href="”https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css”" rel="”stylesheet”">

    添加以下脚本
*   在 app.module.ts 中导入折叠组件
*   在 app.component.html 制造一个塌陷部件。
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

    <link rel="icon" type="image/x-icon" href="favicon.ico">
    <link rel="preconnect" href="https://fonts.gstatic.com">
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
<button type="button" class="btn btn-success" 
    (click)="gfg = !gfg" aria-controls="geeks">
    Click to collapse!
</button>
<hr>
<div id="geeks" [collapse]="gfg">
    <div class="well well-lg card 
        card-block card-header">
        GeeksforGeeks
    </div>
</div>
<br />
<button type="button" class="btn btn-success" 
    (click)="gfg1 = !gfg1" aria-controls="geeks1">
    Click to collapse!
</button>
<hr>
<div id="geeks1" [collapse]="gfg1">
    <div class="well well-lg card 
        card-block card-header">
        GeeksforGeeks
    </div>
</div>
```

## app.module.ts

```ts
import { NgModule } from '@angular/core';

// Importing forms module
import {
    FormsModule,
    ReactiveFormsModule
} from '@angular/forms';
import { BrowserModule }
    from '@angular/platform-browser';
import { BrowserAnimationsModule }
    from '@angular/platform-browser/animations';
import { CollapseModule } from 'ngx-bootstrap/collapse';

import { AppComponent } from './app.component';

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
        CollapseModule.forRoot()
    ]
})
export class AppModule { }
```

**输出:**

![](img/a3d52098531a6625f4f263ea90beaa39.png)

**参考:**T2】https://valor-software.com/ngx-bootstrap/#/collapse