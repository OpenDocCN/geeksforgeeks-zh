# 当 AngularJS 中特定条件为真时，如何显示/隐藏数据？

> 原文: [https://www.geeksforgeeks.org/how-to-show-hide-data-when-the-particular-condition-is-true-in-angularjs/](https://www.geeksforgeeks.org/how-to-show-hide-data-when-the-particular-condition-is-true-in-angularjs/)

在 AngularJS 中，为了隐藏或显示数据或内容，我们可以使用 `ngIf` 结构指令。通过使用这个，我们可以评估条件，然后 `ngIf` 根据条件显示内容。例如，如果 `ngIf` 的条件为真，则显示内容，如果条件为假，则不显示内容。

## 方法:

*   为了给出一个清晰详细的视角，我将使用一个例子来解释这个概念。
*   假设我们有一个对象数组。TypeScript 文件中的对象数组包含技术类和非技术类公司的列表。
*   本实验的目的是显示所有技术类公司的数据，并隐藏所有非技术类公司。
*   为了遍历数组，我们将在 HTML 文件中使用 `ngFor` 指令。
*   实现后，启动服务器。

## 实施:

### `app.component.ts`:

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: [ './app.component.css' ]
})
export class AppComponent  {

companies = [
    {
      name: "Microsoft",
      isTechnical  : true,
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