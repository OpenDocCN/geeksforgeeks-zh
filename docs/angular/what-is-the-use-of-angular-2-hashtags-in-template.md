# Angular 2 标签在模板中有什么用？

> 原文:[https://www . geesforgeks . org/angular-2-hashtags-in-template/](https://www.geeksforgeeks.org/what-is-the-use-of-angular-2-hashtags-in-template/)有什么用

Angular2 hashtag 是一种用于将 DOM 元素声明为变量的语法，这些模板呈现为一个 HTML 文件。

*   **#:** 变量声明
*   **():** 事件绑定
*   **[]:** 属性绑定
*   **[()]:** 双向属性绑定
*   **{{}}:** 插值

模板引用变量是一个小宝石，允许用 Angular 做很多好事。它依赖于一个简单的 hashtag 来创建对模板中元素的引用。
**语法:**

```ts
<input #searchBox keyword="search(searchBox.value)">
```

在上面的语法中，它创建了对**输入**元素的引用，该元素可以在以后的模板中使用。
T3】例:

## java 描述语言

```ts
import {Component} from 'angular2/core';

@Component({
   selector: 'pv-app',
   templateUrl: 'components/harry/hello.component.html'
})

export class pvApp {}import {Component} from 'angular2/core';

@Component({
   selector: 'pv-app',
   templateUrl: 'components/pv/hello.component.html'
})

export class pvApp {}
```

```ts
<input type="text" #pv>
 {{ pv.value }}
```

在上例中， **pv** 引用 HTML 元素对象实例进行输入。所以，pv 拥有 HTML 元素的所有属性和方法。(身份证、姓名等。)