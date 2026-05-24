# 使用 AngularJS

生成二维码

> 原文:[https://www . geeksforgeeks . org/generate-QR-code-using-angularjs/](https://www.geeksforgeeks.org/generate-qr-code-using-angularjs/)

在本文中，我们将看到如何在我们的 Angular 应用程序中生成和显示二维码。二维码是由黑白方块组成的矩阵，可以被相机或智能手机读取。二维码可以存储信息和网址，便于机器人或智能手机用户阅读。在商业场景中，二维码可以用于共享联系信息、发送电子邮件、下载应用程序、共享网址和位置。因此，我们需要知道如何为我们的应用生成一个来跟上市场。

**先决条件:**必须安装 NPM

**环境设置:**

安装角度 CLI 并创建新的角度项目。

```ts
npm i -g @angular/cli
ng new <project-name>
cd <project-name>
```

现在，通过在本地主机上提供应用程序来验证安装:

```ts
ng serve -o
```

你应该看到棱角分明的登陆页面，你就可以走了。现在我们需要安装和注册一个额外的软件包:

```ts
npm install @techiediaries/ngx-qrcode
```

在 app.module.ts 中注册。在 app 文件夹的 **app.module.ts** 文件中更改或复制以下代码。

## 

```ts
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';

// Import this module 
import {NgxQRCodeModule} from '@techiediaries/ngx-qrcode'

@NgModule({
  declarations: [
    AppComponent,
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    NgxQRCodeModule    // Register the module
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

现在让我们创建一个新的组件来显示带有所需数据的二维码。

```ts
ng generate component qrcode
```

这将生成 4 个新文件。此外，它将通过自动注册组件来更新文件 app.module.ts。现在在**二维码** :

## 二维码

```ts
import { Component, OnInit } from '@angular/core';
@Component({
  selector: 'app-qrcode',
  templateUrl: './qrcode.component.html',
  styleUrls: ['./qrcode.component.css']
})
export class QrcodeComponent{ 
  elementType = 'url';
  data = 'https://geeksforgeeks.org/';
}
```

中添加以下代码

这里的元素类型可以是“url”、“img”或“canvas”。url 类型可以编码字符串类型数据。数据变量存储我们想要编码的数据。现在将以下代码添加到**qrcode.component.html**:

## 【qrcode.component.html】

```ts
<ngx-qrcode
  [elementType]="elementType"
  [value]="data">
</ngx-qrcode>
```