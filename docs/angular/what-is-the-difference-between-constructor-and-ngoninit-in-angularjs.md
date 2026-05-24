# AngularJS 中的构造函数和 ngOnInit 有什么区别？

> 原文:[https://www . geesforgeks . org/constructor-and-ngoninit-in-angular js/](https://www.geeksforgeeks.org/what-is-the-difference-between-constructor-and-ngoninit-in-angularjs/)之间的区别是什么

**Constructor:** Constructor 是类的默认方法，它是在安装类时创建的，并确保类及其子部分中角色的正确执行。Angular 最好是 Dependency Injector (DI)，它分析构建器的组件，并在通过调用新的 MyClass()创建新特性时，尝试查找与构建器参数类型匹配的供应商，解析它们并将它们传递给类似的组件。

```ts
new MyClass(someArg);
```

**示例:**

```ts
var AddNumbers= (function () {
    function AddNumbers(x, y) {
        this.x = x;
        this.y = y;
    }
    AddNumbers.prototype.add = function () {
      return this.x + point.x;
    };
    return AddNumbers;
})();

var numbers = new AddNumbers(2, 4);
var additionOfNumbers = numbers.add();
console.log(additionOfNumbers);
```

**输出:**

```ts
6
```

**ngOnInit:** OnInit 是一个名为 Angular 的生命周期小部件，显示 Angular 是为了创建一个组件而制作的。我们必须像这样导入 OnInt 才能使用它(实际上使用 OnInt 不是强制性的，但它被认为是好的)。

**语法:**

```ts
import {Component, OnInit} from '@ angular / core';
```

为了使用它来执行 OnInit 方法，我们应该使用这样一个部分:

**示例:**

```ts
import { Component, OnInit } from '@angular/core';

@Component({
    selector:'app-checkbox',
    templateUrl:'./checkbox.component.html',
    styleUrls: ['./checkbox.component.css']
})

export class CheckboxComponent implements OnInit {
    constructor() {
        console.log('Called Constructor');
    }

    ngOnInit() {
        console.log('Called ngOnInit method');
    }
}
```

**输出:**

```ts
Called Constructor
Called ngOnitit method
```

**注:**类 app 销售

```ts
constructor () {
// First called before ngOnInit ()
}
```

```ts
Oninit () {
// Named after the constructor and named after NgOnChanges()
}

```

在启动 admin 属性后，使用这种交互来应用自定义启动思维。NGOnInit 第一次以目标站点的索引命名，并且在其任何子站点被测试之前命名。仅包含一次指南。

【ngOnInit 与建造师的区别:

*   我们在每一次创业/发布会上都使用 ngOnInit，避免在建筑商那里工作。构造函数应该只用于启动类成员，而不应该做实际的“工作”。
*   所以应该使用构造函数()来设置依赖注入，不要太多。ngOnInit()是一个更好的“起点”——这是解决组件组合的地方/时间。
*   我们使用构造函数()进行所有的初始化/声明。
*   最好避免在构造函数中写实际工作。
*   构造函数()只应该用来初始化类成员，而不应该做实际的“工作”。
*   所以我们应该使用构造函数()来设置依赖注入、类字段初始化等。
*   ngOnInit()是编写“实际工作代码”的更好的地方，我们需要在类实例化后立即执行这些代码。
*   就像从数据库中加载数据一样——在您的 HTML 模板视图中向用户显示。这样的代码应该用 ngOnInit()编写。

**结论:**

*   构造函数初始化类成员。
*   ngOnInit()是一个放置代码的地方，我们需要在类实例化后立即执行这些代码。