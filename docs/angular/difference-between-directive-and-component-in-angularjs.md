# AngularJS 中方向和分量的区别

> 原文:[https://www . geesforgeks . org/instruction-and-component-in-angularjs/](https://www.geeksforgeeks.org/difference-between-directive-and-component-in-angularjs/)

**简介:**
我们将通过简单了解这两个术语、它们的含义以及它们在构建简洁而强大的 AnglarJS 代码方面的行为特征，来开始寻找 Directive 和 Components 之间的区别这一主题。Angular 的发明引入了指令，作为构建动态 web 应用程序的结构框架。指令在操作文档对象模型和创建新的自定义元素时很流行，它们是文档对象模型的一部分。随着 Angular 后期版本(Angular 2 和更高版本，因为 Angular 2 本身依赖于基于组件的结构)的技术升级和各种修改，组件的使用现在引起了开发人员的极大兴趣。此外，组件被称为指令的更简化版本。

**基本定义:**
指令是每当 AngularJs 的 HTML 编译器($compile)在 DOM 中找到它时就会调用的函数。它告诉将指定的行为附加到该 DOM 元素(例如，通过事件侦听器)，或者甚至转换 DOM 元素及其子元素。
组件只是指令的简化版本。更具体地说，组件可以被称为一种带有模板的特殊指令，主要用于基于组件的体系结构。
**例:**

*   **Component-**
    **Syntax:**

    ```ts
    import {Component, View} from 'angular2/angular2';
    @Component ({........
                ........ })
    @View ({............
             ...........})
    ```

    ```ts
    import {Component, View} from 'angular2/angular2';
    @Component({
      selector: 'message'
    })
    @View({
      template: `
          <h6>Hello GeeksforGeeks</h6>
          <h6>This is an example of component</h6> `
    })
    class Message {
      constructor(public version: string) {}
    }
    ```

    **输出:**

    ```ts
    你好极客们这是组件的一个例子
    ```

*   **指令-**
    **语法:**

```ts
import {Directive} from 'angular2/angular2';
@Directive({........
            ........})
```

```ts
import {Directive} from 'angular2/angular2';

@Directive({
    selector: "[myDirective]",
    hostListeners: {
        'click': 'showMessage()'
    }
})
class Message {

    constructor() {}

    showMessage() { 
    console.log('This is an example of directive'); }
}

<button>GeeksforGeeks</button>
```

**输出:**

```ts
Geeksforgeeks
This is an example of directive
```

**解释:**
在上面的例子中，我们已经看到了如何使用 Component 和 Directive 编写简单的 Angular 代码来打印一些消息。在组件的示例中，我们已经看到必须编写视图属性，而对于指令，我们不需要使用视图或模板。现在让我们讨论一下这两者之间的主要区别。
**差异:**

1.  组件总是元素(“E”)，其中指令可以是属性、元素名称、注释或 CSS 类(“E”、“A”、“C”、“M”)。模板是强制属性，并且在组件中总是必需的，但是指令并不总是需要它们。
2.  组件用于将应用程序分解成更小的组件。但是 Directive 被用来设计可重用的组件，这更加面向行为。这就是为什么组件在 Angular 的后期版本中被广泛使用，以使事情变得简单并构建一个基于组件的整体模型。
3.  因为组件有视图，所以可以定义视图封装。而指令没有观点。所以不能在指令中使用视图封装。
4.  尽管组件使编写简单、有效的代码变得更加容易，但它比普通指令具有更简单的配置，它针对基于组件的体系结构进行了优化。但是什么时候不用组件呢？答案是——组件不支持“编译”和“预链接”功能。所以对于操作 DOM 对象，我们应该使用指令。

*   组件永远不应该修改超出自己范围的任何数据或 DOM。指令具有独立的作用域，默认情况下，子级从其父级继承作用域。*   每个 DOM 元素只能有一个组件。一个 DOM 元素中可以有多个指令*   To register component we use @Component meta-data annotation. For directive, we use @Directive meta-data annotation. Two simple examples are shown in the point ‘Example’ above.

    **结论:**
    已经给出了关于该主题的基本研究。是使用组件还是指令，完全取决于为使用编写特定代码的目的。随着新兴技术的出现，大多数网页设计架构都致力于获得基于组件的模型，而这正是我们需要组件的时候。另一方面，指令给了我们很多选择，比如选择器、输入、输出、提供者，让我们创造性地编写代码。