# 角度 ngx 引导标签组件

> 原文:[https://www . geesforgeks . org/angular-ngx-bootstrap-tab s-component/](https://www.geeksforgeeks.org/angular-ngx-bootstrap-tabs-component/)

Angular ngx bootstrap 是一个 bootstrap 框架，与 Angular 一起使用，创建具有很好风格的组件，这个框架非常容易使用，用于制作响应性网站。
在本文中，我们将了解如何在 angular ngx 自举中使用 tab。

**安装语法:**

```ts
npm install ngx-bootstrap --save
```

**进场:**

*   首先，使用上述命令安装 angular ngx 引导程序。
*   在 index.html

    > <link href="”https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css”" rel="”stylesheet”">

    添加以下脚本
*   在模块中导入标签组件
*   在 app.component.html 做一个制表符组件。
*   使用 ng serve 为应用提供服务。

**例 1:**

## index.html

```ts
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8" />
    <title>Demo</title>
    <base href="/" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1" />
    <link href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
        rel="stylesheet" />

    <link rel="icon" type="image/x-icon" href="favicon.ico" />
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link href=
"https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&display=swap"
        rel="stylesheet" />
    <link href=
"https://fonts.googleapis.com/icon?family=Material+Icons"
        rel="stylesheet" />
</head>

<body class="mat-typography">
    <app-root></app-root>
</body>

</html>
```

## app.component.html

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

## app.module.ts

```ts
import { NgModule } from '@angular/core';

// Importing forms module
import { FormsModule, ReactiveFormsModule  } 
from '@angular/forms';
import { BrowserModule }
from '@angular/platform-browser';
import { BrowserAnimationsModule }
from '@angular/platform-browser/animations';
import { TabsModule} from 'ngx-bootstrap/tabs';

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

## app.component.css

```ts
#gfg{
    margin: 10px;
}
```

## app.component.ts

```ts
import { Component, OnInit,LOCALE_ID } from '@angular/core';

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

**输出:**

![](img/149e0ae558d387a80cdfc49bdda57a3e.png)