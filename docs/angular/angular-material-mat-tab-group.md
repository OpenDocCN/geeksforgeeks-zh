# 角形材料垫-标签-组

> 原文:[https://www . geesforgeks . org/angular-mat-mat-tab-group/](https://www.geeksforgeeks.org/angular-material-mat-tab-group/)

Angular Material 是一个 UI 组件库，由 Angular 团队开发，用于构建桌面和移动网络应用程序的设计组件。为了安装它，我们需要在我们的项目中安装 angular，一旦你有了它，你可以输入下面的命令并下载它。 **mat-tab-group** 主要用于我们有多个选项卡要显示时的导航栏需求。

**安装:**

```ts
ng add @angular/material
```

**进场:**

*   First, use the above command to install the angular material.
*   安装完成后,从 app.module.ts 文件中的" @角度/材料/标签"导入 MatTabsModule .
*   Then use the < mat-tab-group > tag to group all items in this group of tags.
*   In the tag, we need to use the tag for each item.
*   We can also set the style of the label according to the position of start, center and end. To do this, we need to use an attribute named mat-align-tab.
*   If we want to change the theme, then we can use the color attribute to change it. In angular, we have three themes, which are main, emphasized and warned.
*   After completing the above steps, start the service or start the project.

**示例:**

```ts
import { NgModule } from '@angular/core'; 
import { BrowserModule } from '@angular/platform-browser'; 
import { FormsModule } from '@angular/forms'; 
import { MatTabsModule } from '@angular/material/tabs'; 

import { AppComponent } from './app.component'; 
import { BrowserAnimationsModule } from 
'@angular/platform-browser/animations';

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