# 如何在 Angular 中将数据从父组件传递给子组件？

> 原文:[https://www . geeksforgeeks . org/如何将数据从父代传递到子代-组件-in-angular/](https://www.geeksforgeeks.org/how-to-pass-data-from-parent-to-child-component-in-angular/)

我们可以使用@Input 指令在 Angular 中将数据从父组件传递给子组件

**使用输入绑定:**@ Input–我们可以在子组件内部使用这个指令来访问父组件发送的数据。这里 app.component 是父组件，cdetail.component 是子组件。

#### 父组件

**app.component.ts** 有两个数组。一个用于 list _ Prog–语言列表，Prog _ details–语言详细信息。

## app.component.ts

```ts
import { Component } from '@angular/core';
import { AbstractControl, FormBuilder, 
        FormGroup } from '@angular/forms';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
export class AppComponent {

    list_prog = ['JAVA', 'C++', 'C', 
            'PYTHON', 'JAVASCRIPT'];

    prog_details = [`Java is a widely used 
    platform independent language. Java was 
    developed by James Gosling.`, `C++ is 
    multi-paradigm and procedural oriented 
    language. Developed by Bjarne Stroustrup.`, 
    `C is a procedural language and 
    developed by Dennis Ritchie`, `Python is 
    a interpreted high level language 
    developed by Guido van Rossum`, 
    `Javascript is a language that conforms 
    the ECMAScript and developed by ECMAScript`];
    options: number;
    curr_info: string;
    prog_title: string;

    constructor() {}

    onClick(lang) {
        switch (lang) {
            case 'JAVA':
                this.options = 0;
                this.curr_info = 
                    this.prog_details[this.options];

                this.prog_title = 
                    this.list_prog[this.options];
                break;
            case 'C++':
                this.options = 1;
                this.curr_info = 
                    this.prog_details[this.options];

                this.prog_title = 
                    this.list_prog[this.options];
                break;
            case 'C':
                this.options = 2;
                this.curr_info = 
                    this.prog_details[this.options];

                this.prog_title = 
                    this.list_prog[this.options];
                break;
            case 'PYTHON':
                this.options = 3;
                this.curr_info = 
                    this.prog_details[this.options];

                this.prog_title = 
                    this.list_prog[this.options];
                break;
            case 'JAVASCRIPT':
                this.options = 4;
                this.curr_info = 
                    this.prog_details[this.options];

                this.prog_title = 
                    this.list_prog[this.options];
                break;
            default:
                break;
        }
    }
}
```

**app.component.html**这里我们已经在父组件中添加了我们的子组件，并传递了两个数据，一个是 prog_title，另一个是 curr_info。但是请确保您已经在子组件中声明了变量**的详细信息和标题**。

## 超文本标记语言

```ts
<div class="container">
    <div class="row">
        <div class="col-md-3"></div>
        <div class="col-md-6">
            <h4 class="makeCenter">
                List of Programming Languages
            </h4>
            <ul class="uList">
                <li *ngFor="let lang of list_prog"
                [ngClass]=
            "{'active': list_prog[options]===lang}" 
            (click)="onClick(lang)" class="lLang">
                    {{lang}}
                </li>
            </ul>
        </div>
    </div>
</div>
<br><br><br>
<app-cdetail [title]="prog_title" 
    [details]="curr_info">
</app-cdetail>
```

#### 子组件

**cdetail.component.ts** 这里我们在子组件中使用了 **@Input()** 指令。现在在子组件中，可以使用父组件传递的数据。

## java 描述语言

```ts
import { Component, Input, OnInit } from '@angular/core';

@Component({
  selector: 'app-cdetail',
  templateUrl: './cdetail.component.html',
  styleUrls: ['./cdetail.component.css']
})
export class CdetailComponent implements OnInit {

  @Input() details: string;
  @Input() title: string;

  constructor() { }

  ngOnInit(): void {
  }

}
```

**cdetail.component.html**

## 超文本标记语言

```ts
<div class="container">
    <div class="row">
        <div class="col-md-4"></div>
        <div class="col-md-4">
            <h3 class="makeCenter">{{title}}</h3>
            <p style="text-align: justify; 
                text-justify: inter-word;">
                {{details}}
            </p>
        </div>
    </div>
</div>
```

### **输出**

![](img/3fae666891db19c6ce6e87df2cf42cdf.png)