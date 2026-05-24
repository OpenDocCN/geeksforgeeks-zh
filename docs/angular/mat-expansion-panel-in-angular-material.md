# <mat-expansion-panel>在</mat-expansion-panel>角材

> 原文:[https://www . geesforgeks . org/mat-expansion-in-panel-in-angular-material/](https://www.geeksforgeeks.org/mat-expansion-panel-in-angular-material/)

**简介:**
Angular Material 是 Angular 团队开发的 UI 组件库，用于构建桌面和移动 web 应用的设计组件。为了安装它，我们需要在我们的项目中安装 angular，一旦你有了它，你可以输入下面的命令并下载它。< mat-expansion-panel >标签是一种具有折叠和展开功能的下拉菜单。

**安装语法:**

```ts
ng add @angular/material
```

**进场:**

*   首先，使用上述命令安装角度材料。
*   安装完成后，从 app.module.ts 文件中的“@ angular/material/expansion module”导入“MatExpansionModule”。
*   然后使用<mat-accordion>标签作为<mat-expansion-panel>标签的父标签。</mat-expansion-panel></mat-accordion>
*   在<mat-accordion>标签中，我们需要对每个项目使用<mat-expansion-panel>标签。</mat-expansion-panel></mat-accordion>
*   对于<mat-expansion-panel>标签，我们有许多子标签，如下表所述。</mat-expansion-panel>
*   完成上述步骤后，就可以开始项目了。

<figure class="table">

| **标签名称** | **属性** |
| <mat-panel-title></mat-panel-title> | 它用于显示面板的标题 |
| <mat-panel-description></mat-panel-description> | 它用于显示有关面板的信息。 |

</figure>

**代码实现:**

## app.module.ts

```ts
import { CommonModule } from '@angular/common'; 
import { NgModule } from '@angular/core'; 
import { FormsModule } from '@angular/forms'; 
import { MatExpansionModule } from '@angular/material'; 

import { AppComponent } from './example.component'; 

@NgModule({ 
  declarations: [AppComponent], 
  exports: [AppComponent], 
  imports: [ 
    CommonModule, 
    FormsModule, 
    MatExpansionModule

  ], 
}) 
export class AppModule {}
```