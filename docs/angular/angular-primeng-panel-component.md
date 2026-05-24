# 角形灌注面板组件

> 原文:[https://www . geesforgeks . org/angular-priming-panel-component/](https://www.geeksforgeeks.org/angular-primeng-panel-component/)

Angular PrimeNG 是一个开源框架，具有一组丰富的本机 Angular UI 组件，用于实现出色的风格，该框架用于非常轻松地制作响应性网站。在本文中，我们将了解如何在 Angular PrimeNG 中使用 Panel 组件。我们还将了解将在代码中使用的属性、事件和样式以及它们的语法。

**面板组件:**它允许我们制作一个包含标题和与该标题相关联的一些内容的元素。

**属性:**

*   **表头:**是面板的表头文本。它是字符串数据类型，默认值为 null。
*   **可折叠:**定义面板的内容是否可以展开和折叠。它是布尔数据类型，默认值为 false。
*   **折叠:**定义面板内容的初始状态。它是布尔数据类型，默认值为 false。
*   **样式:**是组件的内嵌样式。它是字符串数据类型，默认值为 null。
*   **styleClass:** 是组件的样式类。它是字符串数据类型，默认值为 null。
*   **扩展图标:**是切换按钮的扩展图标。它是字符串数据类型，默认值是 pi pi-plus。
*   **折叠图标:**是切换按钮的折叠图标。它是字符串数据类型，默认值是 pi-pi 减。
*   **显示表头:**指定面板的表头是否不能显示。它是布尔数据类型，默认值为真。
*   **过渡选项:**是动画的过渡选项。它是字符串数据类型，默认值是 400 毫秒三次贝塞尔曲线(0.86，0，0.07，1)。
*   **toggler:** 指定 toggler 元素是否切换面板内容。它是字符串数据类型，默认值是图标。

**事件:**

*   **onBeforeToggle:** 是在内容切换之前触发的回调。
*   **onaftertogle:**是内容切换后触发的回调。

**造型:**

*   **p-panel** :是容器元素。
*   **p-panel-标题栏:**是表头部分。
*   **p-panel-title:** 是面板的标题文本。
*   **p-panel-title bar-toggler:**是切换图标。
*   **p-panel-content:** 是面板的内容。

**创建角度应用&模块安装:**

*   **步骤 1:** 使用以下命令创建角度应用程序。

```ts
ng new appname
```

*   **步骤 2:** 创建项目文件夹即 appname 后，使用以下命令移动到该文件夹。

```ts
cd appname
```

*   **步骤 3:** 在给定的目录中安装 PrimeNG。

```ts
npm install primeng --save
npm install primeicons --save
```

**项目结构**:如下图:

![](img/6e2ac1499ceea2e58d3439c1f9f0d39a.png)

**示例 1:** 这是说明如何使用 Panel 组件的基本示例。

## app.component.html

```ts
<h2>GeeksforGeeks</h2>
<h5>PrimeNG Panel Component</h5>
<p-panel header="Angular PrimeNG">
   <p>
      Angular PrimeNG is a framework used 
      with angular to create components 
      with great styling and this framework 
      is very easy to use and is used to 
      make responsive websites.
   </p>
</p-panel>
```

## app.component.ts

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.scss']
})
export class AppComponent {}
```

## app.module.ts

```ts
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";
import { BrowserAnimationsModule } 
    from "@angular/platform-browser/animations";

import { AppComponent } from "./app.component";
import { PanelModule } from "primeng/panel";

@NgModule({
  imports: [BrowserModule, 
              BrowserAnimationsModule, 
            PanelModule],
  declarations: [AppComponent],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

**输出:**

![](img/e757fb4195c800a67cab9cf30c8a5c4f.png)

**示例 2:** 在本例中，我们将了解如何在 Panel 组件中使用*可切换*属性。

## app.component.html

```ts
<h2>GeeksforGeeks</h2>
<h5>PrimeNG Panel Component</h5>
<p-panel header="Angular PrimeNG" toggleable="true"> 
  <p>
    Angular PrimeNG is a framework used 
    with angular to create components with
    great styling and this framework is 
    very easy to use and is used to make
    responsive websites.
  </p>
</p-panel>
```

## app.component.ts

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.scss']
})
export class AppComponent {}
```

## app.module.ts

```ts
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";
import { BrowserAnimationsModule } 
    from "@angular/platform-browser/animations";

import { AppComponent } from "./app.component";
import { PanelModule } from "primeng/panel";

@NgModule({
  imports: [BrowserModule, 
              BrowserAnimationsModule, 
            PanelModule],
  declarations: [AppComponent],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

**输出:**

![](img/b92fb940bf5387ea2aa3b36b48775ee8.png)

**参考:**T2】https://primefaces.org/primeng/showcase/#/panel