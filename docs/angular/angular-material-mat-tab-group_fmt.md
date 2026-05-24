# 角形材料垫-标签-组

> 原文: [https://www.geeksforgeeks.org/angular-material-mat-tab-group/](https://www.geeksforgeeks.org/angular-material-mat-tab-group/)

Angular Material 是一个 UI 组件库，由 Angular 团队开发，用于构建桌面和移动网络应用程序的设计组件。为了安装它，我们需要在我们的项目中安装 angular，一旦你有了它，你可以输入下面的命令并下载它。`mat-tab-group` 主要用于我们有多个选项卡要显示时的导航栏需求。

## 安装:

```ts
ng add @angular/material
```

## 进场:

*   首先，使用上述命令安装 angular material。
*   安装完成后，从 `app.module.ts` 文件中的 `@角度/材料/标签` 导入 `MatTabsModule`。
*   然后使用 `<mat-tab-group>` 标签来将所有项目分组到这个标签组中。
*   在 `<mat-tab-group>` 标签内，我们需要为每个项目使用 `<mat-tab>` 标签。
*   我们还可以根据起始、居中和结束的位置来设置标签的样式。为此，我们需要使用一个名为 `mat-align-tab` 的属性。
*   如果我们想更改主题，那么我们可以使用 `color` 属性来更改它。在 angular 中，我们有三个主题，分别是 `main`、`emphasized` 和 `warned`。
*   完成上述步骤后，启动服务或启动项目。

## 示例:

```ts
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { FormsModule } from '@angular/forms';
import { MatTabsModule } from '@angular/material/tabs';

import { AppComponent } from './app.component';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';

@NgModule({
  imports:
  [ BrowserModule,
    FormsModule,
    MatTabsModule,
    BrowserAnimationsModule],
  declarations: [ AppComponent ],
  bootstrap: [ AppComponent ]
})

export class AppModule { }
```