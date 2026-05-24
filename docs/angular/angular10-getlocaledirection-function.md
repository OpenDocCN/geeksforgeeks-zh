# Angular10 getLocaleDirection()函数

> 原文:[https://www . geeksforgeeks . org/angular 10-getlocaldiedirection-function/](https://www.geeksforgeeks.org/angular10-getlocaledirection-function/)

在这篇文章中，我们将看到什么是 Angular 10 中的 **getLocaleDirection** 以及如何使用它。

getlocaldedidirection是 用来获取给定区域的书写方向。

**语法:**

```ts
getLocaleDirection(locale: string): 'ltr' | 'rtl'
```

**模块:**getLocaleDirection 使用的模块为:

*   **公共模块**

**进场:**

*   创建要使用的角度应用程序
*   在 app.module.ts 中导入 LOCALE_ID，因为我们需要使用 getLocaleDirection 导入区域设置。

```ts
import { LOCALE_ID, NgModule } from '@angular/core';
```

*   在 app.component.ts 中导入 getLocaleDirection 和 LOCALE_ID
*   将 LOCALE_ID 作为公共变量注入。
*   在 app.component.html，使用字符串插值显示局部变量
*   使用 ng serve 为 angular app 服务，以查看输出。

**参数:**

*   **区域设置:**包含带有规则的区域设置代码的字符串。

**返回值:**

*   **字符串:**包含书写方向的字符串。

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
        getLocaleDirection, 
        TranslationWidth } 
        from '@angular/common';

import {Component, 
        Inject,OnInit, 
        LOCALE_ID } 
        from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html'
})
export class AppComponent {
    dir = getLocaleDirection(this.locale);
    constructor(
        @Inject(LOCALE_ID) public locale: string,){}
      }
```

## app.component.html

```ts
<h1>
   GeeksforGeeks
</h1>
<p>Locale Direction is : {{dir}}</p>
```

**输出:**

![](img/39c5d134d12cf68453536dc7816a2ccf.png)

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
        getLocaleDirection, 
        TranslationWidth } 
        from '@angular/common';

import {Component, 
        Inject,
        OnInit, 
        LOCALE_ID } 
        from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html'
})
export class AppComponent {
    dir = getLocaleDirection(this.locale);
    a=''
    constructor(
        @Inject(LOCALE_ID) public locale: string,){
            if(this.dir=='ltr'){
                this.a='left to right';
            }
        }
      }
```

## app.component.html

```ts
<h1>
   GeeksforGeeks
</h1>
<p><b>{{ a }}</b> is the direction</p>
```

**输出:**

![](img/e8e4787a329a975684d5b4a46c3a7321.png)

**参考:**[](https://angular.io/api/common/getLocaleCurrencyName)**[https://angular.io/api/common/getLocaleDirection](https://angular.io/api/common/getLocaleDirection)**