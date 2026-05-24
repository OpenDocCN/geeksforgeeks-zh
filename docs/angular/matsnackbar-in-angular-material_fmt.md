# 角材中的倒圆角条

> 原文: [https://www.geeksforgeeks.org/matsnackbar-in-angular-material/](https://www.geeksforgeeks.org/matsnackbar-in-angular-material/)

Angular Material 是 Angular 团队开发的 UI 组件库，用于构建桌面和移动 web 应用的设计组件。为了安装它，我们需要在我们的项目中安装 angular，一旦你完成了，你可以输入下面的命令并下载它。MatSnackBar 用于在执行任何操作时从屏幕底部显示信息或文本。

## 安装语法

```ts
ng add @angular/material
```

## 进场

*   首先，使用上述命令安装 angular material。
*   安装后，在 `app.module.ts` 文件中从 `@angular/material/snack-bar` 导入 `MatSnackBarModule`。
*   首先，我们需要为 `MatSnackbar` 创建一个实例。然后我们需要调用一个按钮点击函数。
*   使用此示例，我们可以访问内置的 `open()` 函数。
*   现在我们需要提及消息的持续时间。
*   完成上述步骤后，启动服务或启动项目。

## 代码实现

### app.module.ts

```ts
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { FormsModule } from '@angular/forms';

import { AppComponent } from './app.component';
import { BrowserAnimationsModule } from
    '@angular/platform-browser/animations';
import {MatSnackBarModule} from '@angular/material/snack-bar';
import { MatButtonModule } from '@angular/material/button';

@NgModule({
    imports: [
        BrowserModule,
        FormsModule,
        MatButtonModule,
        MatSnackBarModule,
        BrowserAnimationsModule
    ],
    declarations: [ AppComponent ],
    bootstrap: [ AppComponent ]
})
export class AppModule { }
```