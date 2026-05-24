# angular 10 getLocaleMonthNames()函数

> 原文:[https://www . geeksforgeeks . org/angular 10-getlocalemonthnames-function/](https://www.geeksforgeeks.org/angular10-getlocalemonthnames-function/)

在本文中，我们将看到 Angular 10 中的 **getLocaleMonthNames** 是什么以及如何使用它。

getLocaleMonthNames 用于获取给定地区的月份。

**语法:**

```ts
getLocaleMonthNames(locale: string, formStyle: FormStyle, 
                         width: TranslationWidth):
                         ReadonlyArray<string>
```

**模块:**getLocaleMonthNames 使用的模块是:

*   CommonModule

**进场:**

*   创建要使用的角度应用程序
*   在 app.module.ts 中导入 LOCALE_ID，因为我们需要为使用 getLocaleMonthNames 导入区域设置。

```ts
import { LOCALE_ID, NgModule } from '@angular/core';
```

*   在 app.component.ts 导入 FormStyle、getLocaleMonthNames、TranslationWidth 和 LOCALE_ID 中
*   注入 LOCALE_ID 作为公共变量，并使用 LOCALE 变量编写获取星期几的代码。
*   在 app.component.html，使用字符串插值显示局部变量
*   使用 ng serve 为 angular app 服务，以查看输出。

**参数:**

*   **地区:**有规则的地区代码。
*   **表格样式:** 显示日期的表格样式
*   **宽度:**取总宽度。

**返回值:**

*   **数组:**月份名称的数组。

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
        getLocaleMonthNames, 
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
    for = getLocaleMonthNames(this.locale, 
    FormStyle.Standalone, 
    TranslationWidth.Wide);
    constructor(
        @Inject(LOCALE_ID) public locale: string,){}
      }
```

## app.component.html

```ts
<h1>
   GeeksforGeeks
</h1>
<p>Months of the year is: {{for}}</p>
```

**输出:**

![](img/c27b9fcc2b03a7fb3a97f63eafa3f755.png)

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
        getLocaleMonthNames, 
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
    day = getLocaleMonthNames(this.locale, 
    FormStyle.Standalone, 
    TranslationWidth.Wide);
    constructor(
        @Inject(LOCALE_ID) public locale: string,){
            console.log(this.day)
        }
      }
```

**输出:**

![](img/ee539b762c07f62f8f73201fb96a0382.png)

**参考:**[](https://angular.io/api/common/getLocaleDayNames)**[https://angular.io/api/common/getLocaleMonthNames](https://angular.io/api/common/getLocaleMonthNames)**