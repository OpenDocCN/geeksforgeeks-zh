# 如何在 Angular 8 中为数组中的值创建超链接？

> 原文:[https://www . geeksforgeeks . org/如何从角度数组创建值超链接-8/](https://www.geeksforgeeks.org/how-to-create-a-hyperlink-for-values-from-an-array-in-angular-8/)

**简介:**
在 angular 8 中，我们可以使用*ngFor 为数组中存在的所有值创建超链接。

**方法:**
1)首先在中声明并初始化数组。ts 文件。
2)然后使用*ngFor 指令迭代数组。
3)在中使用此*ngFor 指令。html 文件，我们可以根据需要使用它。
4)一旦实施完成，就为项目服务。

**语法:**
启动项目的语法。

```ts
ng serve --open
```

**代码实现:**

**app.component.html:**

```ts
<div *ngFor = "let item of data"> 
  <a [attr.href]="item.url">
   {{item.name}}
  </a>
</div>
```

**app . component . ts:**T2】

```ts
import { Component } from '@angular/core';
@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: [ 
  `a{
     text-decoration: none;
     color:black;
     cursor: pointer
     }
  `
  ]
})
export class AppComponent  {

  data=[
    {
      name:"GeeksForGeeks",
      url:"www.geeksforgeeks.org"
    },
    {
      name:"Google",
      url:"www.google.com"
    },
    {
      name:"HackerRank",
      url:"www.hackerrank.com"
    }
  ]

}
```

**输出:**

![](img/986a0d1ab33724b28b2326763286ae07.png)