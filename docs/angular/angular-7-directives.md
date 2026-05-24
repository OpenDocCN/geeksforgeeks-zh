# 角度 7 |指令

> 原文:[https://www.geeksforgeeks.org/angular-7-directives/](https://www.geeksforgeeks.org/angular-7-directives/)

Angular 7 中的指令是用 decorator @Directive 声明的 Typescript 类。这些是文档对象模型(DOM)指令集，决定了如何实现逻辑。
角度指令可分为三种类型:

1.  **组件指令:**组成主类，由**@组件**声明。它包含运行时组件处理、实例化和使用的细节。
    **示例:**它包含某些参数，其中一些参数在本例中显示。

## java 描述语言

```tshtml
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
```

1.  下面讨论三个参数:
    *   **选择器:**告知指定组件开始和结束的模板标签。
    *   **模板 URL:** 由用于组件的模板组成。
    *   **样式 URL:**是数组类型，由模板使用的所有样式格式文件组成。
2.  **结构指令:**结构指令操作 DOM 元素。这些指令前面有*号。例如，*ngIf 和*ngFor。
    **例:**我们来看看*ng-if-else 和*ng-for 的实现。利用它们，我们对工作日和周末进行分类。
    **组件文件:**

## java 描述语言

```tshtml
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  Weekdays:Array =[
'Sunday', 'Monday', 'Tuesday',
'Wednesday', 'Thursday', 'Friday', 'Saturday']
}
```

1.  **模板文件:**

## 超文本标记语言

```tshtml
<div *ngFor="let day of Weekdays">
<ng-container *ngIf =
    "(day == 'Saturday' || day == 'Sunday'); else elseTemplate">
  <h1>{{day}} is a weekend</h1>
</ng-container>
<ng-template #elseTemplate>
  <h1>{{day}} is not a weekend</h1>
</ng-template>
</div>
```