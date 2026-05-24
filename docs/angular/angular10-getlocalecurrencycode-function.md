# angular 10 getLocaleCurrencyCode()函数

> 原文:[https://www . geeksforgeeks . org/angular 10-getlocalecurrencycode-function/](https://www.geeksforgeeks.org/angular10-getlocalecurrencycode-function/)

在本文中，我们将看到 Angular 10 中的 **getLocaleCurrencyCode** 是什么以及如何使用。

getLocaleCurrencyCode 是 用来获取给定地区的默认货币代码。

**语法:**

```ts
getLocaleCurrencyCode(locale: string): string | null
```

**模块:**getLocaleCurrencyCode 使用的模块为:

*   **公共模块**

**进场:**

*   创建要使用的角度应用程序
*   在 app.module.ts 中导入 LOCALE_ID，因为我们需要导入 LOCALE 才能使用 getLocaleCurrencyCode。

```ts
import { LOCALE_ID, NgModule } from '@angular/core';
```

*   在 app.component.ts 中导入 getLocaleCurrencyCode 和 LOCALE_ID
*   将 LOCALE_ID 作为公共变量注入。
*   在 app.component.html，使用字符串插值显示局部变量
*   使用 ng serve 为 angular app 服务，以查看输出。

**参数:**

*   **区域设置:**包含带有规则的区域设置代码的字符串。

**返回值:**

*   **字符串:**包含货币符号的字符串。

**例 1:**

## app.module.ts

```ts
import { LOCALE_ID, NgModule } 
        from '@angular/core';
import { BrowserModule } 
        from '@angular/platform-browser';

import { AppRoutingModule } 
        from './app-routing.module';
import { AppComponent } 
        from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  providers: [
      { provide: LOCALE_ID, useValue: 'en-GB' },
  ],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## app.component.ts

```ts
import {FormStyle,
        getLocaleCurrencyCode, 
        TranslationWidth } 
        from '@angular/common';

import { Component, 
          Inject,OnInit, 
          LOCALE_ID } 
          from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html'
})
export class AppComponent {
    code = getLocaleCurrencyCode(this.locale);
    constructor(
        @Inject(LOCALE_ID) public locale: string,){}
      }
```

## app.component.html

```ts
<h1>
   GeeksforGeeks
</h1>
<p>Currency code is : {{code}}</p>
```

**输出:**

![](img/c5afe65259ccb905d43bfa2b0d592da5.png)

**例 2:**

## app.module.ts

```ts
import { LOCALE_ID, NgModule } 
        from '@angular/core';
import { BrowserModule } 
        from '@angular/platform-browser';

import { AppRoutingModule } 
        from './app-routing.module';
import { AppComponent } 
        from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  providers: [
      { provide: LOCALE_ID, useValue: 'en-GB' },
  ],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## app.component.ts

```ts
import {FormStyle,
        getLocaleCurrencyCode, 
        TranslationWidth } 
        from '@angular/common';

import {Component, 
        Inject, 
        LOCALE_ID } 
        from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html'
})
export class AppComponent {
    code = getLocaleCurrencyCode(this.locale);
    constructor(
        @Inject(LOCALE_ID) public locale: string,){}
      }
```

## app.component.html

```ts
<h1>
   GeeksforGeeks
</h1>
<p>Currency code is : {{code}}</p>

<p>
    {{code}}100
    {{code}}200 
    {{code}}300
    {{code}}400
    {{code}}500
</p>
```

**输出:**

![](img/5d82e44c5b959a716fea1ca57cdbbc68.png)

**参考:**[](https://angular.io/api/common/getLocaleCurrencyName)**[https://angular.io/api/common/getLocaleCurrencyCode](https://angular.io/api/common/getLocaleCurrencyCode)**