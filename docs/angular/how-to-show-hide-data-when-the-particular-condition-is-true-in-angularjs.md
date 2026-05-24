# 当 AngularJS 中特定条件为真时，如何显示/隐藏数据？

> 原文:[https://www . geeksforgeeks . org/当特定条件为真时如何显示-隐藏-数据-in-angularjs/](https://www.geeksforgeeks.org/how-to-show-hide-data-when-the-particular-condition-is-true-in-angularjs/)

在 AngularJS 中，为了隐藏或显示数据或内容，我们可以使用 ***ngIf** 结构指令。通过使用这个，我们可以评估条件，然后 ***ngIf** 根据条件显示内容。例如，如果*ngIf 的条件为真，则显示内容，如果条件为假，则不显示内容。

**方法:**

*   In order to give a clear and detailed point of view, I will use an example to explain this concept.
*   Suppose we have an array of objects. The objects in ts files and arrays contain lists of technical and non-technical companies.
*   The purpose of this experiment is to display the data of all technical companies and hide all non-technical companies.
*   To traverse the array, we will use the *ngFor directive in. Html file.
*   After the implementation, start the server.

**实施:**

**app . component . ts:**

## Javascript

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: [ './app.component.css' ]
})
export class AppComponent  {

  companies = [
    {
      name: "Microsoft",
      isTechnical  : true,
    },

    {
      name: "GeeksForGeeks",
      isTechnical : true
    },

    {
      name: "Netflix",
      isTechnical : false
    },
    {
      name: "TCS",
      isTechnical : true
    }
  ]
}
```