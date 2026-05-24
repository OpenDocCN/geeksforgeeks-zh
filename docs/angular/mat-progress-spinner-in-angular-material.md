# <mat-progress-spinner>在</mat-progress-spinner>角材

> 原文:[https://www . geesforgeks . org/mat-progress-spinner-in-angular-material/](https://www.geeksforgeeks.org/mat-progress-spinner-in-angular-material/)

Angular Material 是一个 UI 组件库，由 Angular 团队开发，用于构建桌面和移动网络应用程序的设计组件。为了安装它，我们需要在我们的项目中安装 angular，一旦你有了它，你可以输入下面的命令并下载它。
**<mat-progress-spinner>**和 **< mat-spinner >** 标签用于指示事件或活动的进度。根据它们的类型，它们以圆周方式运动。

**安装:**

```ts
ng add @angular/material
```

**进场:**

*   首先，使用上述命令安装角度材料。
*   安装完成后，从 app.module.ts 文件中的“@ angular/material/progress-spinner”导入“MatProgressSpinnerModule”。
*   要使用旋转器，我们需要简单地使用<mat-spinner>标签。</mat-spinner>
*   它们是两种类型的进度条，像确定的和不确定的。
*   不确定微调器不会旋转，但在不确定的情况下，微调器会连续旋转。
*   对于确定类型的旋转器，我们需要给出值来显示它们。
*   如果我们想改变主题，那么我们可以使用 color 属性来改变它。在 angular 中，我们有 3 个主题，它们是主要的、强调的和警告的。
*   完成上述步骤后，就可以开始项目了。

**代码实现:**

## app.module.ts

```ts
import { CommonModule } from '@angular/common'; 
import { NgModule } from '@angular/core'; 
import { FormsModule } from '@angular/forms'; 
import { MatProgressSpinnerModule } from '@angular/material'; 

import { AppComponent } from './example.component'; 

@NgModule({ 
  declarations: [AppComponent], 
  exports: [AppComponent], 
  imports: [ 
    CommonModule, 
    FormsModule, 
    MatProgressSpinnerModule

  ], 
}) 
export class AppModule {}
```