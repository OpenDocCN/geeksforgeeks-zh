# Angular ngx Bootstrap Timepicker 组件

> 原文：[https://www.geeksforgeeks.org/angular-ngx-bootstrap-timepicker-component/](https://www.geeksforgeeks.org/angular-ngx-bootstrap-timepicker-component/)

Angular ngx bootstrap 是一个 Bootstrap 框架，与 Angular 一起使用，用于创建具有优良样式的组件。这个框架非常易于使用，适用于制作响应式网站。
在本文中，我们将了解如何在 Angular ngx bootstrap 中使用 Timepicker。

**安装语法：**

```ts
npm install ngx-bootstrap --save
```

**步骤：**

*   首先，使用上述命令安装 `ngx-bootstrap`。
*   在 `index.html` 文件中添加以下样式表链接：
    > <link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" rel="stylesheet">
*   在模块中导入 `TimepickerModule` 组件。
*   在 `app.component.html` 中，制作一个更精致的组件。
*   使用 `ng serve` 为应用提供服务。

**示例：**

## index.html

```ts
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8" />
    <title>Demo</title>
    <base href="/" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" rel="stylesheet" />

    <link rel="icon" type="image/x-icon" href="favicon.ico" />
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&display=swap" rel="stylesheet" />
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet" />
</head>

<body class="mat-typography">
    <app-root></app-root>
</body>

</html>
```

## app.component.html

```ts
<div id="gfg1">
    <timepicker [(ngModel)]="gfg"></timepicker>

    <pre class="alert alert-info">
        Time: {{gfg}}
    </pre>
</div>
```

## app.module.ts

```ts
import { NgModule } from '@angular/core';

// Importing forms module
import { FormsModule, ReactiveFormsModule } from '@angular/forms';
import { BrowserModule } from '@angular/platform-browser';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
import { TimepickerModule } from 'ngx-bootstrap/timepicker';

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
    TimepickerModule.forRoot()
  ]
})
export class AppModule { }
```

## app.component.css

```ts
#gfg1 {
    margin: 10px;
}
```

## app.component.ts

```ts
import { Component, OnInit, LOCALE_ID } from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
export class AppComponent {
    gfg: Date = new Date();
}
```

**输出：**

![](img/9199320847b337a10be9aab15fa9511d.png)