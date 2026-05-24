# 在 Angular 中，注释和装饰有什么区别？

> 原文:[https://www . geeksforgeeks . org/角度注释和装饰器的区别是什么/](https://www.geeksforgeeks.org/what-are-the-differences-between-an-annotation-and-a-decorator-in-angular/)

虽然注释者和装饰者在 Angular 中都有相同的 **@** 符号，但它们都是不同的语言特征。

**注释:**这是硬编码的语言特征。注释只是在类上设置的元数据，用于反映元数据库。当用户注释一个类时，编译器在该类上创建一个名为**注释**的属性，在其中存储一个**注释**数组，然后尝试实例化一个与注释同名的对象，将元数据传递给构造函数。注释在 AngularJs 中没有预定义，所以我们可以自己命名它们。

*   **例:**

    ```ts
    @ComponentAnnotation
    ```

**注释的特点:**

*   Comments are hard-coded.
*   Comments are used by AtScript and Traceur compilers.
*   Reflect metadata database

**注意:**现在 AngularJs 从 AtScript 切换到了 TypeScript，但是现在也支持注释。

**例:**此处组件标注为**组件标注**进一步使用。

```ts
import { 
  ComponentAnnotation as Component,
} from '@angular/core';

export class ComponentAnnotation extends DirectiveMetadata {

  constructor() {

  }
}
```

**装饰器:**一个**装饰器**是一个向类、其成员或其方法参数添加元数据的函数。装饰器只是一个函数，它让您可以访问需要装饰的目标。有四种类型的装饰者，它们都在下面提到:

**装饰器的类型:**

*   类装饰器如@组件、@模块
*   Attribute decorators such as @Input, @Output
*   Method decorators such as @HostListener
*   Parameter decorator such as @ injective

**装饰者的特征:**

*   Decorator is predefined in AngularJs.
*   Decorators are used by the TypeScript compiler.
*   Decorators are used to attach metadata to classes, objects and methods.

**例:**

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'hi',
  template: '<div>GeeksForGeeks</div>',
})
export class Geeks{
  constructor() {
    console.log('GeeksForGeeks');
  }
}
```

**批注与装饰器的区别:**

| annotate and comment on | Decorator |
| Used by Traceur compiler | Used by Typescript compiler |
| Annotations are just metadata set on a class using the Reflect Metadata library. | The Decorator corresponds to the function called on the class. |
| Label the attribute **used to create the storage array and label** . | Decotor is a function that gets the object that needs to be decorated. |
| They are hard coded. | They are not hard coded. |
| Exp .注释的导入：从“@棱角分明/核心”导入{组件注释为组件}； | Exp。 Import of decorator: import {Component }； from @angular/core; |

**结论:**在 AngularJS 中，注释者和装饰者之间存在非常显著的差异。Angular 支持装饰器和注释。这是一个遗留问题，因为 Angular2 从 AtScript 交换到了 TypeScript。装饰器是 AngularJs 的默认设置，但是你也可以使用注释。