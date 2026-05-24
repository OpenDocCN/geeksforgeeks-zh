# 角度预调快速拨号组件

> 原文:[https://www . geesforgeks . org/angular-priming-speed dial-component/](https://www.geeksforgeeks.org/angular-primeng-speeddial-component/)

Angular PrimeNG 是一个开源框架，具有一组丰富的本机 Angular UI 组件，用于实现出色的风格，该框架用于非常轻松地制作响应性网站。在本文中，我们将了解如何在 Angular PrimeNG 中使用 SpeedDial 组件。我们还将了解将在代码中使用的属性、事件和样式以及它们的语法。

**快速拨号组件**:用于显示按下按钮时使用浮动按钮动作可以完成的许多主要动作。

**属性:**

*   **id:** 是元素的唯一标识符。它是字符串数据类型，默认值为 null。
*   **模型**:是定义动作项的 MenuModel 实例。它属于对象数据类型，默认值为空。
*   **可见**:指定叠加的可见性。它是布尔数据类型，默认值为 false。
*   **类名**:是元素的样式类。它是字符串数据类型，默认值为 null。
*   **样式**:是元素的内嵌样式。它属于对象数据类型，默认值为空。
*   **方向**:指定动作的开启方向。它是字符串数据类型，默认值为 up。
*   **过渡延时**:是每个动作项的过渡延时步骤，为数字数据类型，默认值为 30。
*   **类型**:指定动作的开启类型。它是字符串数据类型，默认值为线性。
*   **半径**:是*圆类型的半径，为数字数据类型，默认值为 0。
*   **掩码**:指定是否在快速拨号后面显示一个掩码元素，为布尔数据类型，默认值为 false。
*   **禁用**:指定组件是否禁用。它是布尔数据类型，默认值为 false。
*   **隐藏点击外部**:指定在外部点击时动作是否关闭。它是布尔数据类型，默认值为真。
*   **buttonClassName** :是按钮元素的样式类。它是字符串数据类型，默认值为 null。
*   **按钮样式**:是按钮元素的内嵌样式。它属于对象数据类型，默认值为空。
*   **按钮模板**:是按钮元素的模板。它接受任何类型的数据&默认值为空。
*   **maskClassName** :是遮罩元素的样式类。它是字符串数据类型，默认值为 null。
*   **遮罩样式**:是遮罩元素的内嵌样式。它属于对象数据类型，默认值为空。
*   **显示图标**:是按钮元素的显示图标。它是字符串数据类型，默认值是 pi pi-plus。
*   **隐藏图标**:是按钮元素的隐藏图标。它是字符串数据类型，默认值为 null。
*   **旋转图标**:用于定义隐藏图标不存在时旋转显示图标。它是布尔数据类型，默认值为真。

**事件:**

*   **onVisibleChange** :是元素可见性改变时触发的回调。
*   **onClick** :是点击按钮元素时触发的回调。
*   **onShow** :动作可见时触发的回调。
*   **on side**:是动作隐藏时触发的回调。

**造型:**

*   **p-speeddial:** 是容器元素。
*   **p-快速拨号按键:**是快速拨号的按键元素。
*   **p-速度达-蒙版:**是速度达的蒙版元素。
*   **p-快速拨号列表:**是动作列表。
*   **p-快速拨号项**:用于执行列表中的每个动作项。

**创建角度应用&模块安装:**

**步骤 1:** 使用以下命令创建角度应用程序。

```ts
ng new appname
```

**步骤 2:** 创建项目文件夹即 appname 后，使用以下命令移动到该文件夹。

```ts
cd appname
```

**步骤 3:** 在给定的目录中安装 PrimeNG。

```ts
npm install primeng --save
npm install primeicons --save
```

**项目结构:**如下图:

![](img/6e2ac1499ceea2e58d3439c1f9f0d39a.png)

**示例 1:** 这是说明如何使用快速拨号组件的基本示例。

## app.component.html

```ts
<div>
  <h2>GeeksforGeeks</h2>
  <h5>PrimeNG SpeedDial Component</h5>
  <p-speedDial [model]="gfg"></p-speedDial>
</div>
```

## app.module.ts

```ts
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";
import { RouterModule } from "@angular/router";
import { BrowserAnimationsModule } 
    from "@angular/platform-browser/animations";

import { AppComponent } from "./app.component";
import { ProgressSpinnerModule } 
    from "primeng/progressspinner";
import { RippleModule } from "primeng/ripple";
import { SpeedDialModule } from "primeng/speeddial";

@NgModule({
  imports: [
    BrowserModule,
    BrowserAnimationsModule,
    ProgressSpinnerModule,
    SpeedDialModule,
    RippleModule,
    RouterModule.forRoot([{ path: "", 
        component: AppComponent }]),
  ],
  declarations: [AppComponent],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

## app.component.ts

```ts
import { Component, OnInit } from "@angular/core";
import { MenuItem, MessageService } from "primeng/api";

@Component({
  selector: "my-app",
  templateUrl: "./app.component.html",
  styleUrls: ["./app.component.scss"],
  providers: [MessageService],
})
export class AppComponent {
  gfg: MenuItem[];

  constructor(private messageService: MessageService) {}

  ngOnInit() {
    this.gfg = [
      {
        icon: "pi pi-check",
      },
    ];
  }
}
```

**输出:**

![](img/c1ffa488f6cb40dd3beca05f9f663d64.png)

**示例 2:** 在本例中，我们将了解如何在快速拨号组件中使用*半径*属性。

## app.component.html

```ts
<div class="card">
  <div style="height: 500px; position: relative" 
       class="speeddial-circle-demo">
    <p-speedDial
      [model]="gfg"
      radius="80"
      [transitionDelay]="80"
      type="circle"
      buttonClassName="p-button-warning">
    </p-speedDial>
  </div>
</div>
```

## app.module.ts

```ts
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";
import { RouterModule } from "@angular/router";
import { BrowserAnimationsModule } 
    from "@angular/platform-browser/animations";

import { AppComponent } from "./app.component";
import { ProgressSpinnerModule } from "primeng/progressspinner";
import { RippleModule } from "primeng/ripple";
import { SpeedDialModule } from "primeng/speeddial";

@NgModule({
  imports: [
    BrowserModule,
    BrowserAnimationsModule,
    ProgressSpinnerModule,
    SpeedDialModule,
    RippleModule,
    RouterModule.forRoot([{ path: "", 
        component: AppComponent }]),
  ],
  declarations: [AppComponent],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

## app.component.ts

```ts
import { Component, OnInit } from "@angular/core";
import { MenuItem, MessageService } from "primeng/api";

@Component({
  selector: "my-app",
  templateUrl: "./app.component.html",
  styleUrls: ["./app.component.scss"],
  providers: [MessageService],
})
export class AppComponent {
  gfg: MenuItem[];

  constructor(private messageService: MessageService) {}

  ngOnInit() {
    this.gfg = [
      {
        icon: "pi pi-pencil",
      },
      {
        icon: "pi pi-refresh",
      },
      {
        icon: "pi pi-trash",
      },
      {
        icon: "pi pi-upload",
      },
      {
        icon: "pi pi-external-link",
      },
    ];
  }
}
```

**输出:**

![](img/c640614e7862ba7957ca9a20f3c16065.png)

**参考:**T2】https://primefaces.org/primeng/showcase/#/speeddial