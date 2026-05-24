# 角度灌注输入组组件

> 原文:[https://www . geesforgeks . org/angular-priming-input group-component/](https://www.geeksforgeeks.org/angular-primeng-inputgroup-component/)

Angular PrimeNG 是一个开源框架，具有一组丰富的本机 Angular UI 组件，用于实现出色的风格，该框架用于非常轻松地制作响应性网站。在本文中，我们将了解如何在角度素数中使用输入组组件。

**输入组组件**允许用户输入内容。

**创建角度应用&模块安装:**

*   **步骤 1:** 使用以下命令创建角度应用程序。

    ```ts
    ng new appname
    ```

*   **步骤 2:** 创建项目文件夹(即 appname)后，使用以下命令移动到该文件夹。

    ```ts
    cd appname
    ```

*   **步骤 3:** 在给定的目录中安装 PrimeNG。

    ```ts
    npm install primeng --save
    npm install primeicons --save
    ```

**项目结构**:如下图。

![](img/6e2ac1499ceea2e58d3439c1f9f0d39a.png)

**示例 1:** 这是展示如何使用 InputGroup 组件的基本示例

## app.component.html

```ts
<h2>GeeksforGeeks</h2>
<h5>PrimeNG InputGroup component</h5>

<div class="p-col-12 p-md-4">
  <div class="p-inputgroup">
    <input type="text" pInputText placeholder="InputGroup" />
    <input type="text" pInputText placeholder="InputGroup" />
    <input type="text" pInputText placeholder="InputGroup" />
  </div>
</div>
```

## app.module.ts

```ts
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";
import { FormsModule } from "@angular/forms";
import { HttpClientModule } from "@angular/common/http";
import { BrowserAnimationsModule } from 
    "@angular/platform-browser/animations";

import { AppComponent } from "./app.component";

import { InputTextModule } from "primeng/inputtext";

@NgModule({
  imports: [
    BrowserModule,
    BrowserAnimationsModule,
    InputTextModule,
    FormsModule,
  ],
  declarations: [AppComponent],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

**输出:**

![](img/1d8b1c224db6888351bea73ad619503e.png)

**示例 2:** 在本例中，我们将了解如何在 InputGroup 组件中使用 disabled 属性

## app.component.html

```ts
<h2>GeeksforGeeks</h2>
<h5>PrimeNG InputGroup component</h5>

<div class="p-col-12 p-md-4">
  <div class="p-inputgroup">
    <input type="text" disabled pInputText placeholder="InputGroup" />
    <input type="text" disabled pInputText placeholder="InputGroup" />
    <input type="text" disabled pInputText placeholder="InputGroup" />
  </div>
</div>
```

## app.module.ts

```ts
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";
import { FormsModule } from "@angular/forms";
import { HttpClientModule } from "@angular/common/http";
import { BrowserAnimationsModule } from 
    "@angular/platform-browser/animations";

import { AppComponent } from "./app.component";

import { InputTextModule } from "primeng/inputtext";

@NgModule({
  imports: [
    BrowserModule,
    BrowserAnimationsModule,
    InputTextModule,
    FormsModule,
  ],
  declarations: [AppComponent],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

**输出:**

![](img/b5f5a86723343b398b7f6810fdeca8d4.png)

**参考:**T2】https://primefaces.org/primeng/showcase/#/inputgroup