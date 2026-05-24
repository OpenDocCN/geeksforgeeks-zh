# 在 Angular 中，注释和装饰器有什么区别？

> 原文：[https://www.geeksforgeeks.org/what-are-the-differences-between-an-annotation-and-a-decorator-in-angular/](https://www.geeksforgeeks.org/what-are-the-differences-between-an-annotation-and-a-decorator-in-angular/)

虽然注释和装饰器在 Angular 中都有相同的 `@` 符号，但它们都是不同的语言特征。

**注释：** 这是硬编码的语言特征。注释只是在类上设置的元数据，用于反映元数据库。当用户注释一个类时，编译器在该类上创建一个名为 `annotations` 的属性，在其中存储一个 `annotations` 数组，然后尝试实例化一个与注释同名的对象，将元数据传递给构造函数。注释在 AngularJs 中没有预定义，所以我们可以自己命名它们。

*   **例：**

```ts
@ComponentAnnotation
```

**注释的特点：**

*   注释是硬编码的。
*   注释被 AtScript 和 Traceur 编译器使用。
*   反射元数据库。

**注意：** 现在 AngularJs 从 AtScript 切换到了 TypeScript，但是现在也支持注释。

**例：** 此处组件标注为 `ComponentAnnotation` 进一步使用。

```ts
import { 
  ComponentAnnotation as Component,
} from '@angular/core';

export class ComponentAnnotation extends DirectiveMetadata {
  constructor() {
  }
}
```

**装饰器：** 一个 `装饰器` 是一个向类、其成员或其方法参数添加元数据的函数。装饰器只是一个函数，它让您可以访问需要装饰的目标。有四种类型的装饰器，它们都在下面提到：

**装饰器的类型：**

*   类装饰器如 `@Component`、`@Module`
*   属性装饰器如 `@Input`、`@Output`
*   方法装饰器如 `@HostListener`
*   参数装饰器如 `@Inject`

**装饰者的特征：**

*   装饰器在 AngularJs 中是预定义的。
*   装饰器被 TypeScript 编译器使用。
*   装饰器用于将元数据附加到类、对象和方法上。

**例：**

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'hi',
  template: '<div>GeeksForGeeks</div>',
})
export class Geeks {
  constructor() {
    console.log('GeeksForGeeks');
  }
}
```

**注释与装饰器的区别：**

| 注释 | 装饰器 |
| :--- | :--- |
| 被 Traceur 编译器使用 | 被 TypeScript 编译器使用 |
| 注释只是使用 Reflect Metadata 库在类上设置的元数据。 | 装饰器对应于在类上调用的函数。 |
| 标记属性**用于创建存储数组和标记**。 | 装饰器是一个获取需要装饰的对象的函数。 |
| 它们是硬编码的。 | 它们不是硬编码的。 |
| 例：注释的导入：`import { ComponentAnnotation as Component } from '@angular/core';` | 例：装饰器的导入：`import { Component } from '@angular/core';` |

**结论：** 在 AngularJS 中，注释和装饰器之间存在非常显著的差异。Angular 支持装饰器和注释。这是一个遗留问题，因为 Angular2 从 AtScript 交换到了 TypeScript。装饰器是 AngularJs 的默认设置，但是你也可以使用注释。