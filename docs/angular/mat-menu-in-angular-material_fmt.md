# Angular Material 中的 <mat-menu> 组件

> 原文：[https://www.geeksforgeeks.org/mat-menu-in-angular-material/](https://www.geeksforgeeks.org/mat-menu-in-angular-material/)

Angular Material 是一个 UI 组件库，由 Angular 团队开发，用于构建桌面和移动网络应用程序的设计组件。为了安装它，我们需要在我们的项目中安装 Angular。一旦你有了它，你可以输入下面的命令并下载它。

`<mat-menu>` 充当一种下拉菜单或菜单部分，每当用户点击任何按钮时，它就会展开或打开。

**安装语法：**

```
ng add @angular/material
```

**步骤：**

*   首先，使用上述命令安装 Angular Material。
*   安装完成后，从 `app.module.ts` 文件中的 `@angular/material/menu` 导入 `MatMenuModule`。
*   除此之外，它还从 `app.module.ts` 文件中的 `@angular/material/button` 导入 `MatButtonModule`。
*   然后使用 `<mat-menu>` 标签将该菜单标签内的所有项目分组。
*   在 `<mat-menu>` 标签中，我们需要为下拉列表中显示的每个项目使用 `<mat-menu-item>` 标签。
*   我们有像 `position` 和 `position` 这样的属性来定制下拉菜单的打开方向。
*   完成上述步骤后，就可以开始项目了。

**代码实现：**

## app.module.ts

```
import { CommonModule } from '@angular/common';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { MatMenuModule, MatButtonModule } from '@angular/material';

import { AppComponent } from './example.component';

@NgModule({
  declarations: [AppComponent],
  exports: [AppComponent],
  imports: [
    CommonModule,
    FormsModule,
    MatMenuModule,
    MatButtonModule
  ],
})
export class AppModule {}
```