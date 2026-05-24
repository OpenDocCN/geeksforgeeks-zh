# 将内容投影到含有 ng 内容的组件中

> 原文:[https://www . geesforgeks . org/projecting-content-in-components-with-ng-content/](https://www.geeksforgeeks.org/projecting-content-into-components-with-ng-content/)

在 Angular 中，有很多方法可以在我们的应用程序中传递数据。但是有时我们有复杂的 HTML/typescript 代码需要从外部传入组件。因此，如果我们想要简化代码，而不想在 server-component.html 内部设置 Html/typescript 代码，那么我们可以在服务器组件标签的开始和结束元素之间(即在`‹app-server›‹∕app-server›`标签之间)编写这段代码，并相应地更改组件变量。

**示例:**

```tshtml
serverElement : 
{type:'server', name:'some-name', content:'some-value'}
```

**app-component.html**

```tshtml
<div class="container-fluid">
<div class="row">
<div class="col-md-6 col-sm-1">
<app-server-element *ngFor=
         "let ele of serverElements" [element]="ele">
    <div class="card-text" 
        *ngIf="ele.type === 'server'" style="color: yellow;" > 
         Element name rendered is {{ele.name}} 
         Element content rendered is {{ele.content}}
    </div>
</app-server-element>
</div>
</div>
</div>
```

**ng-content:**
在 server-component.html 模板中需要添加一个特殊的指令(`‹ng-content›‹∕ng-content›`)，在我们想要渲染内容的地方。它充当您放置在组件中的钩子，用于标记组件应该在开始和结束标记之间添加任何内容的位置。
T5】server-component.html

```tshtml
<div class="card">
    <div class="card-body"> 
        <h5 class="card-header text-uppercase">
            <strong>{{element.type}}</strong>
        </h5>
            <ng-content></ng-content> 
    </div>
</div>
```

**服务器元素:**

```tshtml
{type:'server', name:'some-name', content:'some-value'}
```

**app-component.ts**

```tshtml
import { Component } from '@angular/core';
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
serverelements=[{type:'server', 
                name:"TestServer",
                comp:'Just a Test!'}];
onAddedServer(data: {servername: string, 
                     servercomponent: string}){
  this.serverelements.push({
    type:'server',
    name:data.servername,
    comp:data.servercomponent
  })
}
```

**输出:**

```tshtml
Element name rendered is "some-name"
Element content rendered is "some-value"
```

这里，我们通过 ng-content Hook 添加了 HTML 代码，我们将它添加在开始和结束标签之间，因此它将被投影到服务器组件中。这是一个很好的特性，如果我们考虑构建可重用的小部件，这是很特别的。但是如果它的 HTML 代码更复杂，那么属性绑定并不是最好的解决方案，因为 angular 会在那里转义 Html 文本，然后 ng-content 是最好的工具。