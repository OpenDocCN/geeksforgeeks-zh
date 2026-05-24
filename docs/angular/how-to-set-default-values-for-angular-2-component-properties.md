# 如何设置 Angular 2 组件属性的默认值？

> 原文:[https://www . geeksforgeeks . org/如何设置角度 2 组件属性的默认值/](https://www.geeksforgeeks.org/how-to-set-default-values-for-angular-2-component-properties/)

在 Angular 2 中，我们可以使用 Input Decorator 在两个组件(从父组件到子组件)之间传递变量值。使用这些输入装饰器，我们还可以设置属性的默认值。下面我详细阐述了如何设置角度 2 组件的默认值。

**语法:**

```ts
@Input() PropertyName = Default Value  /* @Input country = 'India' */
```

**进场:**

*   首先编码。关于需求的 html 文件。
*   然后在子组件中包含默认属性。
*   现在使用@Input()装饰器用默认值初始化属性。
*   我们还应该从“@angular/core”导入输入装饰器。
*   初始化完成后，使用 HTML 文件中的属性在浏览器中显示。

**导入语法:**

```ts
import { Input } from '@angular/core';
```

**通过代码实现:**
**app . component . html:**

```ts
<p>Welcome to GeeksforGeeks </p>
<app-child [country] = "countryName"></app-child>
```

**app . component . ts:**T2】

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: [ './app.component.css' ]
})
export class AppComponent  {
  constructor() { }
  ngOnInit() {}
  countryName = 'India';
}
```

**child.component.ts:**

```ts
import { Component, Input, OnInit} from '@angular/core';

@Component({
  selector: 'app-child',
  templateUrl: './child.component.html'
})
export class ChildComponent implements OnInit {
  constructor() { }
  ngOnInit() {}

  @Input() country = 'Australia';
  @Input() capital = 'New Delhi';

}
```

**child.component.html:**

```ts
<p> Country is : {{country}} </p>
<p> Capital is : {{capital}} </p>
```

**结论:**
当我们把国家财产作为‘印度’传递时，它就会被显示出来。但是当涉及到资本时，因为我们没有传递任何值，所以它在 child.component.ts 文件中显示默认值。

**输出:**

![](img/2d2cb015894dd4f6fe3d1bae26cde4f9.png)