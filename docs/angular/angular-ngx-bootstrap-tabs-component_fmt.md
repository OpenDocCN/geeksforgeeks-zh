# Angular ngx Bootstrap Tabs 组件

> 原文：[https://www.geeksforgeeks.org/angular-ngx-bootstrap-tabs-component/](https://www.geeksforgeeks.org/angular-ngx-bootstrap-tabs-component/)

Angular ngx bootstrap 是一个与 Angular 一起使用的 Bootstrap 框架，用于创建样式精美的组件。该框架非常易于使用，适用于制作响应式网站。
在本文中，我们将了解如何在 Angular ngx bootstrap 中使用标签页（tabs）。

## 安装语法

```ts
npm install ngx-bootstrap --save
```

## 进程

*   首先，使用上述命令安装 Angular ngx bootstrap。
*   在 `index.html` 文件中添加以下样式表链接：
    > <link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" rel="stylesheet">
*   在模块中导入标签页组件。
*   在 `app.component.html` 中创建一个标签页组件。
*   使用 `ng serve` 为应用提供服务。

## 示例 1

### index.html

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

### app.component.html

```ts
<div id='gfg'>
    <tabset>
        <tab heading="GeeksforGeeks">
            Tabs component in Angular ngx bootstrap
        </tab>
        <tab heading="GeeksforGeeks1">
            Tabs component in Angular ngx bootstrap
        </tab>
        <tab heading="GeeksforGeeks2">
            Tabs component in Angular ngx bootstrap
        </tab>
    </tabset>
</div>
```

### app.module.ts

```ts
import { NgModule } from '@angular/core';

// Importing forms module
import { FormsModule, ReactiveFormsModule } from '@angular/forms';
import { BrowserModule } from '@angular/platform-browser';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
import { TabsModule } from 'ngx-bootstrap/tabs';

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
    TabsModule.forRoot()
  ]
})
export class AppModule { }
```

### app.component.css

```ts
#gfg{
    margin: 10px;
}
```

### app.component.ts

```ts
import { Component, OnInit, LOCALE_ID } from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
export class AppComponent {
    itemStringsLeft = [
        'Windstorm',
        'Bombasto',
        'Magneta',
        'Tornado'
    ];
}
```

## 输出

![](img/149e0ae558d387a80cdfc49bdda57a3e.png)