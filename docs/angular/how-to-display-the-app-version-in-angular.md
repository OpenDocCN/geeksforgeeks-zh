# 如何在 Angular 中显示 app 版本？

> 原文:[https://www . geesforgeks . org/如何显示应用程序版本/in-angular/](https://www.geeksforgeeks.org/how-to-display-the-app-version-in-angular/)

Angular 是谷歌基于客户端 TypeScript 的前端网络框架。Angular 8 是一个非常棒的、可重用的用户界面框架，它有助于开发人员构建单页应用程序。一般来说，所有的角度 2+项目或应用被称为角度应用。早期的版本叫做 Angular.js，Angular 是 Angular.js 的完全重写，它具有丰富而有用的特性。

**进场:**

*   为了知道版本，首先我们需要从“@angular/core”导入‘VERSION’。
*   导入它的原因是它是一个包含属性的对象，我们可以用它来了解版本。
*   导入后，现在使用导入版本的“完整”密钥访问版本。
*   检索值后，将其分配给一个变量，然后使用字符串插值在 HTML 文件中显示。
*   完成上述实现后，开始项目。

**代码实现:**

1.  **app.component.ts:**

    ## java 描述语言

    ```ts
    import { Component, VERSION } from '@angular/core';

    @Component({
      selector: 'app-root',
      templateUrl: './app.component.html',
      styleUrls: [ './app.component.css' ]
    })

    export class AppComponent  {
      version = VERSION.full;
    }
    ```