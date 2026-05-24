# 如何使用 Angular 8 在打字的基础上让输入呈现为句子大小写？

> 原文:[https://www . geeksforgeeks . org/如何让输入显示为基于句子大小写的输入使用 angular-8/](https://www.geeksforgeeks.org/how-to-make-input-appear-as-sentence-case-based-on-typing-using-angular-8/)

在本例中，我们将看到如何使用 angular8 基于键入使输入出现句子大小写。

**方法:**

*   First, we need to write code for input types in HTML files.
*   After the input type is written as text in HTML, we can bind the value of the input field by using bidirectional binding, that is, using ngModel.
*   Now, in order to make the sentences in the input field case consistent, we can use the ngModelChange event to manipulate the values according to the needs.
*   Make sure that you are importing "FormsModule" from "@angular/forms".
*   Now, after importing the module, we need to implement this function in the ts file. In this file, we can use regex to modify the input value according to the sentence case and other requirements, and display it in the input field.
*   Once the above steps are completed, start or service the project to run.

**代码实现:**

**app . component . ts:**

## Javascript

```ts
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
export class AppComponent {
    inputvalue = ''

    changeToSentenceCase(event) {

        this.inputvalue = event.replace(/\b\w/g, 
            event => event.toLocaleUpperCase());

    }
}
```