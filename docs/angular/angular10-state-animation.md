# 角度 10 状态动画

> 原文:[https://www.geeksforgeeks.org/angular10-state-animation/](https://www.geeksforgeeks.org/angular10-state-animation/)

在本文中，我们将看到 Angular 10 中的状态是什么，以及如何使用它。

angular 10 中的 **状态** 用于创建包含动画状态和过渡的动画触发器。

**语法:**

```ts
State(name, style, options)
```

**模块:**状态使用的模块是:

*   **动画**

**进场:**

*   创建一个需要使用的角度应用程序。
*   在 app.module.ts 中，导入浏览器动画引擎。
*   在 app.component.html，制作一个包含动画元素的 div。
*   在 app.component.ts 中，导入要使用的触发器、状态、样式、过渡和动画。
*   制作包含动画名称和样式的状态。
*   使用 ng serve 为 angular app 服务，以查看输出。

**参数:**

*   **名称:**设置识别字符串。
*   **样式:**与状态关联的一组 CSS 样式。
*   **选项:** 参数，调用时可以传递给状态。

**返回值:**

*   **动画状态元数据:** 封装新状态数据的对象。

**示例:**

## app.module.ts

```ts
import { LOCALE_ID, NgModule } 
from '@angular/core';
import { BrowserModule } 
from '@angular/platform-browser';
import {BrowserAnimationsModule}
from '@angular/platform-browser/animations';
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
    AppRoutingModule,
    BrowserAnimationsModule
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
import { 
  // State is imported here
  trigger, 
  state, 
  style, 
  transition, 
  animate } from '@angular/animations';
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: [ './app.component.css' ],
  animations: [

    trigger('geek',[

      // State is used here      
      state('clr', style({
        'background-color': '#91fff4',
        transform: 'translateX(0)'
      })),

      // State is used here
      state('clr1', style({
        'background-color': '#7356a8',
        transform: 'translateX(100px)'
      })),
      transition('clr => clr1',animate(1200)),
      transition('clr1 => clr',animate(1000))
    ])
  ]
})
export class AppComponent  {
  state = 'clr';
  anim(){
    this.state == 'clr' ? 
    this.state = 'clr1' : this.state = 'clr';
  }
}
```

## app.component.html

```ts
<h1>GeeksforGeeks</h1>
<button (click)='anim()'>Animate</button>
<br>
<br>
<div 
  style="width: 150px; height: 100px; 
         border-radius: 5px;"
  [@geek]='state'>
</div>
```

**输出:**

![](img/ac67909d3a9e48ae046e5db375fc2922.png)

**参考:**T2】https://angular.io/api/animations/state