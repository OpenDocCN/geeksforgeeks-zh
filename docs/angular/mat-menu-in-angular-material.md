# <mat-menu>在</mat-menu>角材

> 原文:[https://www.geeksforgeeks.org/mat-menu-in-angular-material/](https://www.geeksforgeeks.org/mat-menu-in-angular-material/)

Angular Material 是一个 UI 组件库，由 Angular 团队开发，用于构建桌面和移动网络应用程序的设计组件。为了安装它，我们需要在我们的项目中安装 angular，一旦你有了它，你可以输入下面的命令并下载它。
<菜单>充当一种下拉菜单或菜单部分，每当用户点击任何按钮时，它就会展开或打开。

**安装语法:**

```ts
ng add @angular/material
```

**进场:**

*   首先，使用上述命令安装角度材料。
*   安装完成后，从 app.module.ts 文件中的“@angular/material/menu”导入“MatMenuModule”。
*   除此之外，它还从 app.module.ts 文件中的“@angular/material/button”导入“MatButtonModule”。
*   然后使用<mat-menu>标签将该菜单标签内的所有项目分组。</mat-menu>
*   在<mat-menu>标签中，我们需要为下拉列表中显示的每个项目使用<mat-menu-item>标签。</mat-menu-item></mat-menu>
*   我们有像“位置”和“位置”这样的属性来定制下拉菜单的打开方向。
*   完成上述步骤后，就可以开始项目了。

**代码实现:**

## app.module.ts

```ts
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