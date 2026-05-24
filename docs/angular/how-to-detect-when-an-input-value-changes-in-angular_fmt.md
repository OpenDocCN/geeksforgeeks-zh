# 如何检测@Input()值何时在 Angular 中发生变化？

> 原文: [https://www.geeksforgeeks.org/how-to-detect-when-an-input-value-changes-in-angular/](https://www.geeksforgeeks.org/how-to-detect-when-an-input-value-changes-in-angular/)

## 介绍

`@Input()`基本上是一个将属性绑定为输入的装饰器。它用于传递数据，即从一个组件到另一个组件的属性绑定，或者我们可以说，从父组件到子组件。它与 DOM 元素绑定在一起。当 DOM 元素值更改时，Angular 会自动用更改后的值更新该属性。在这里，我们将看看如何使用它。

## 方法

*   带`@Input()`的双向绑定
*   使用 `ngOnChange()` 和 `@Input()` 进行单向绑定

### 双向绑定

双向绑定使用 `ngModel` 指令将输入和输出结合在单一表示法中。双向绑定的表示法是 `[()]`。

以下是我们将如何实现双向绑定。我们有一个父组件 `FormComponent` 和一个子组件 `ChildComponent`。当用户在父组件的文本输入字段中输入任何内容时，子组件会检测到它。

```ts
// Implementation of Two-way binding:
```

在这里，我们创建一个父组件，并向其中添加子组件。
*form.component.html*

```html
<div style="border: 1px solid rgb(46, 93, 194); 
            height: 25vh; 
            width: 35vw; 
            padding: 10px 10px; 
            margin: 20px;" >
    <b>Type here : </b>
       <input type="text" [(ngModel)]='text' /> 
    <child [message]='text'></child> 
</div>
```

在子组件中，我们传递了一个属性 `message`，它保存了使用 `ngModel` 由输入元素绑定的值。下面是 `FormComponent` 类:

*FormComponent*

```ts
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-form',
  templateUrl: './form.component.html',
  styleUrls: ['./form.component.scss']
})
export class FormComponent implements OnInit {

  constructor() { }

  ngOnInit(): void {
  }
  public text : string;
}
```

这种变化将反映在子组件中。`message` 将在此显示。这是代码:
*child.component.html*

```html
<div style="border:1px solid rgb(53, 71, 131);
            width:30vw; 
            height: 12vh;
            padding: 10px 10px;
            margin:20px">
  <h4> You entered <span>{{message}}</span></h4>
</div>
```

在子组件类中，我们将导入 `Input`，以便检测来自 `FormComponent` 类的 `message`。

*ChildComponent*

```ts
import { Component, OnInit, Input } from '@angular/core';

@Component({
  selector: 'child',
  templateUrl: './child.component.html',
  styleUrls: ['./child.component.scss']
})
export class ChildComponent {
  //message will detect the input from FormComponent.
  @Input() message:string; 
  constructor() { }
}
```

这都是关于双向绑定的。现在让我们看看如何使用单向绑定。

### 使用 `ngOnChange()` 和 `@Input()` 进行单向绑定

下面是我们将如何使用 `ngOnChange()` 来绑定输入。`ChildComponent` 的代码将与双向绑定的情况相同。但是，`FormComponent` 将调用 `onChange()` 方法。这是它的代码。
*form.component.html*

```html
<div style="border: 1px solid rgb(46, 93, 194);
            height: 25vh; 
            width: 35vw; 
            padding: 10px 10px;
            margin: 20px;" >

    <b>Type here : </b>
       <input type="text" 
         [ngModel]='text' 
          (ngModelChange)='onChange($event)' />
    <child [message]='text'></child>
</div>
```

请注意这个组件和前面显示双向绑定的代码之间的区别。这里，`ngModel` 和 `ngModelChange` 都与输入元素绑定。因为我们使用的是 `onChange()`，所以不需要使用 `@Input()` 来检测更改。

*FormComponent*

```ts
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-form',
  templateUrl: './form.component.html',
  styleUrls: ['./form.component.scss']
})
export class FormComponent implements OnInit {

  constructor() { }

  ngOnInit(): void {
  }
  public text : string;
  onChange(UpdatedValue : string) :void
  {
    this.text = UpdatedValue;
  }
}
```

## 输出

<video class="wp-video-shortcode" id="video-448299-1" width="640" height="360" loop="1" autoplay="" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200704204540/Output9.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200704204540/Output9.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200704204540/Output9.mp4)</video>