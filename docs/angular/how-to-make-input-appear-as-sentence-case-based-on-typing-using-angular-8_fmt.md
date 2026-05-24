# 如何使用 Angular 8 在打字的基础上让输入呈现为句子大小写？

> 原文: [https://www.geeksforgeeks.org/how-to-make-input-appear-as-sentence-case-based-on-typing-using-angular-8/](https://www.geeksforgeeks.org/how-to-make-input-appear-as-sentence-case-based-on-typing-using-angular-8/)

在本例中，我们将看到如何使用 `Angular 8` 基于键入使输入出现句子大小写。

**方法:**

*   首先，我们需要在 HTML 文件中为输入类型编写代码。
*   在 HTML 中将输入类型写为 `text` 后，我们可以使用双向绑定，即使用 `ngModel`，来绑定输入字段的值。
*   现在，为了使输入字段中的句子大小写一致，我们可以使用 `ngModelChange` 事件根据需要操作值。
*   确保你从 `"@angular/forms"` 导入了 `FormsModule`。
*   导入模块后，我们需要在 `ts` 文件中实现这个功能。在这个文件中，我们可以使用正则表达式根据句子大小写和其他要求修改输入值，并将其显示在输入字段中。
*   完成上述步骤后，启动或服务项目以运行。

**代码实现:**

**app.component.ts:**

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