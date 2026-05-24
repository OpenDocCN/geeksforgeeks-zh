# 在 Angular 10 中显示或隐藏子组件

> 原文: [https://www.geeksforgeeks.org/show-or-hide-children-components-in-angular-10/](https://www.geeksforgeeks.org/show-or-hide-children-components-in-angular-10/)

**先决条件:** 必须安装 [Angular](https://www.geeksforgeeks.org/angular-8-introduction/)。

在本文中，我们将看到如何在 Angular 中显示或隐藏子组件。

*   让我们从创建一个新项目开始。创建一个新文件夹并初始化一个新的 Angular 项目。运行该项目以验证其是否正常工作。

```ts
ng new myProject
ng serve -o
```

*   这将在当前目录中创建一个新项目。现在，我们可以清空 `app.component.html` 文件并创建一个子组件来演示如何显示或隐藏它。

```ts
ng generate component comp1
```

*   现在设置部分结束。让我们将这个组件添加到我们的 `app.component.html` 文件中：

```ts
<app-comp1></app-comp1>
```

*   我们将创建一个按钮来显示和隐藏组件。让我们将按钮代码添加到 `app.component.html` 文件中。

```ts
<button type="button" (click)="showhideUtility()">
    {{buttonTitle}}
</button>
```

*   这里的 `showhideUtility()` 是一个方法，`buttonTitle` 是一个变量，我们需要在 `app.component.ts` 文件中定义它们。

## app.component.ts

```ts
import { Component } from '@angular/core';
@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
   export class AppComponent {
   title = 'myProject';
   buttonTitle:string = "Hide";
   showhideUtility(){
   }
}
```

*   我们的子组件仍然是空白的，所以让我们添加一些内容。转到 `comp1.component.html` 并添加以下代码：

```ts
<div>
   This is the Child Component
</div>
```

*   并在 `comp1.component.css` 中添加一些 CSS 以获得漂亮的视图：

```ts
div{
height:200px;
width: 200px;
border: 2px lightblue solid;
border-radius: 10px;
background-color: lightgreen;
}
```

*   现在回到 `app.component.ts`，添加一个新属性 `visible`，它将是一个布尔变量，用于定义显示/隐藏状态。当用户触发显示隐藏方法时，它应该翻转 `visible` 变量的值。所以最终，我们的 `app.component.ts` 将如下所示：

## app.component.ts

```ts
import { Component } from '@angular/core';
@Component({
 selector: 'app-root',
 templateUrl: './app.component.html',
 styleUrls: ['./app.component.css']
})
export class AppComponent {
 title = 'myProject';
 buttonTitle:string = "Hide";
 visible:boolean = true;
 showhideUtility(){
   this.visible = this.visible?false:true;
   this.buttonTitle = this.visible?"Hide":"Show";
 }
}
```