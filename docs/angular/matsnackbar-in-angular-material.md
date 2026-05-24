# 角材中的倒圆角条

> 原文:[https://www . geesforgeks . org/matsnackbar-in-angular-material/](https://www.geeksforgeeks.org/matsnackbar-in-angular-material/)

Angular Material 是 Angular 团队开发的 UI 组件库，用于构建桌面和移动 web 应用的设计组件。为了安装它，我们需要在我们的项目中安装 angular，一旦你完成了，你可以输入下面的命令并下载它。MatSnackBar 用于在执行任何操作时从屏幕底部显示信息或文本。

**安装语法:**

```ts
ng add @angular/material
```

**进场:**

*   First, use the above command to install the angular material.
*   After installation, import "MatSnackBarModule" from "@ angular/material/ snack bar" in app.module.ts file.
*   First, we need to create an instance for' matsnackbar'. Then we need to invoke a button click function.
*   Using this example, we can access the built-in open () function.
*   Now we need to mention the duration of the message.
*   After completing the above steps, start the service or start the project.

**代码实现:**

## app . module . ts

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