# angular 10 get number of currency digits()函数

> 原文:[https://www . geeksforgeeks . org/angular 10-getnumberof currency digits-function/](https://www.geeksforgeeks.org/angular10-getnumberofcurrencydigits-function/)

在本文中，我们将看到 Angular 10 中的**getnumber of currency digits**是什么以及如何使用它。

getNumberOfCurrencyDigits 是 用于获取给定货币的小数位数。

**语法:**

```ts
getNumberOfCurrencyDigits(code: string): number
```

**模块:**getnumberof currency digits 使用的模块为:

*   CommonModule

**进场:**

*   创建要使用的角度应用程序
*   在 app.module.ts 中导入 LOCALE_ID，因为我们需要使用 getNumberOfCurrencyDigits 导入区域设置。

```ts
import { LOCALE_ID, NgModule } from '@angular/core';
```

*   在 app.component.ts 中导入 getNumberOfCurrencyDigits 和 LOCALE_ID
*   将 LOCALE_ID 作为公共变量注入。
*   在 app.component.html，使用字符串插值显示局部变量
*   使用 ng serve 为 angular app 服务，以查看输出。

**参数:**

*   **代码:**货币代码

**返回值:**

*   **数字:** 小数位数。

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
        getNumberOfCurrencyDigits, 
        TranslationWidth} 
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
    for = getNumberOfCurrencyDigits(this.locale);
    constructor(
        @Inject(LOCALE_ID) public locale: string,){}
      }
```

## app.component.html

```ts
<h1>
   GeeksforGeeks
</h1>
<p>currency digit number is: {{for}}</p>
```

**输出:**

![](img/ea37685634bc9c523f495232e7cc6f00.png)

**参考:**[](https://angular.io/api/common/getLocaleCurrencyName)**[https://angular.io/api/common/getNumberOfCurrencyDigits](https://angular.io/api/common/getNumberOfCurrencyDigits)**