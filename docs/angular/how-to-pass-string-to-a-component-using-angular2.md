# 如何使用 Angular2 将字符串传递给组件？

> 原文:[https://www . geeksforgeeks . org/如何使用-angular2 将字符串传递给组件/](https://www.geeksforgeeks.org/how-to-pass-string-to-a-component-using-angular2/)

在 angular2 中，一个组件被认为是一个具有自己的逻辑和数据的**‘视图’**。数据绑定是将数据值与其对应的表示相结合的过程。对于组件，字符串值可以直接作为字符串文字传递，也可以通过将字符串文字存储在变量中来传递。有 3 种方法可以将字符串值传递给 angular2 中的组件。组件的模板部分描述了字符串值绑定。

**将字符串值从组件的类传递给组件:**这里，消息变量将从类的构造函数或通过使用角度事件绑定(用户输入)获得其值。

**语法:**

```ts
<component>{{message}}</component>
```

**示例:**这是将字符串传递给组件的最简单方式。组件“AppComponent”有一个名为“app-display”的选择器，显示模板指向“app.component.html”。当组件的类包含字符串数据时，组件可以通过插入“content”变量来访问它。

*   **T2T4

    ```ts
    import { Component } from '@angular/core';
    @Component({ 
        selector: 'app-display',
        template: `app.component.html`
    })
    export class AppComponent {
        content : string = "Hello World";
    }
    ```** 
*   **app.component.html**T3

    ```ts
    <p>GeeksForGeeks</p>
    <app-display> {{content}} </app-display>
    ```

    T4】
*   **输出:**

    ```ts
    GeeksForGeeks
    Hello World
    ```

**2。在嵌套组件之间传递字符串值:**这里，**输入字段**是属性，消息是保存所需字符串的变量。组件之间的交互可以使用两个装饰器来完成。

1.  **@Input()**
2.  **@Output()**

**语法:**

```ts
<component [inputField]="message"></component>
```

**1。@Input decorator:** 使用类中的@Input decorator 和组件 decorator 的指令属性，可以将一个字符串从父组件传递给子组件。当子组件中的变量用@Input decorator 声明时，子组件可以从父组件模板“接收”该变量。

**示例:**容器组件(父组件)应该将“send”的值传递给嵌套组件(子组件)。使用属性绑定，绑定目标“message”从绑定源“send”获取内容。父组件的组件装饰器的指令属性指定需要使用**“子组件”**。在接收端，子代有@Input 装饰器，它从父代接收字符串并相应地使用它。

*   **```ts
    import { Component } from '@angular/core';

    @Component({
      selector: 'parent',
      template: 'parent.component.html',
      directives: [ChildComponent];

    })
    export class parentComponent {
      send: string;

      constructor() {
        this.send = 'A message from parent';
      }
    }
    ```** 
*   ****parent.component.html**T3

    ```ts
    <p>GeeksForGeeks</p>
    <p>I am parent</p>
    <child [message]="send"></child>
    ```

    T4】**
*   ****T2T4

    ```ts
    import { Component, Input } from '@angular/core';

    @Component({
      selector: 'child',
      template: 'child.component.html',
    })
    export class childComponent {
      @Input() message: string;
    }
    ```**** 
*   ****child.component.html**T3

    ```ts
    <p>I am child</p>
    <child>{{message}}</child>
    ```

    T4】**
*   ****输出:**

    ```ts
    GeeksForGeeks
    I am parent
    I am child
    A message from parent
    ```** 

****2。@Output decorator:** 这种方法用于从子节点发出数据，由父节点接收。对于@Output 装饰器来装饰嵌套类的任何属性，属性类型必须是事件。嵌套组件将数据传回其容器的唯一方法是使用事件。要传递的数据称为事件负载。在 angular2 中，事件是用 EventEmitter 对象定义的。**

****示例:**子组件将使用@Output 属性拥有一个 EventEmitter 对象的实例。调用一个函数(这里是按钮点击)来触发字符串的传递。另一方面，使用指令装饰器将子组件绑定到它的父组件将使用另一个可以根据兴趣使用的函数来接收有效负载。**

*   ****```ts
    import { Component } from '@angular/core';

    @Component({
      selector: 'parent',
      template: `parent.component.html`,
      directives: [ChildComponent]
    })

    export class ParentComponent {

      parentText = 'I am Parent';

      constructor () { }

      recievemsg($text) {
        this.parentText = $text;
      }
    }
    ```**** 
*   ******parent.component.html**T3

    ```ts
    <p> {{ username }} </p>
    <child (messageEmitter)="recievemsg()"></child>
    ```

    T4】****
*   ******T2T4

    ```ts
    import { Component, Output, EventEmitter } from '@angular/core';

    @Component({
      selector: 'child-',
      template: `child.component.html`,
    })

    export class ChildComponent {
      message: string = "Message From Child";

      // New EventEmitter object for emitting string
      @Output() messageEmitter = new EventEmitter<string>();

      sendmsg() {

        // Emit message on click
        this.messageEmitter.emit(this.message); 
      }
    }
    ```****** 
*   ******child.component.html**T3

    ```ts
    <p>GeeksForGeeks </p>
    <p>Child called</p>
    <button (click)="sendmsg()"> Send Message </button>
    ```

    T4】****
*   ******输出:**

    ```ts
    GeeksForGeeks
    Child called
    I am Parent
    Message from child
    ```**** 

******注:**以上两种方法用于通过插值将字符串传递给组件。****

******将字符串值直接传递给组件，无需插值:**这里，“message”本身就是字符串，作为组件 inputField 属性的输入给出。****

******语法:******

```ts
**<component inputField="message"></component>
(or)
<component [inputField]="'message'"></component>
(or) 
<component inputField="{{'message'}}"></component>** 
```

******示例:**以下示例涵盖了所有三种方法。****

*   ******T2T4

    ```ts
    import { Component } from '@angular/core';
    @Component({
      selector: 'example',
      templateUrl: './app.component.html',  
    })
    export class AppComponent  {
    }
    ```****** 
*   ******app.component.html**T4

    ```ts
    <example name="GeeksForGeeks1"></example>
    <example [name]="'GeeksForGeeks2'"></example>
    <example name=" {{'GeeksForGeeks3'}} "></example>
    ```**** 
*   ******输出:**

    ```ts
    GeeksForGeeks1
    GeeksForGeeks2
    GeeksForGeeks3
    ```****