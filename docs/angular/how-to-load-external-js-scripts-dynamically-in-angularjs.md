# 如何在 AngularJS 中动态加载外部 JS 脚本？

> 原文:[https://www . geesforgeks . org/how-load-external-js-scripts-dynamic-in-angularjs/](https://www.geeksforgeeks.org/how-to-load-external-js-scripts-dynamically-in-angularjs/)

任务是在运行时从存储在系统中的 CDN 或 JS 文件中动态加载一个 JS 代码。例如，按下按钮或某个事件。

每当我们想要加载脚本文件时，我们必须使用**[document . createelement](https://www.geeksforgeeks.org/html-dom-createelement-method/ target=)**创建一个“脚本”类型的元素。然后，我们将它的 src 属性指定为脚本的位置，要么是 CDN，要么是本地 js 文件。一旦这样做了，我们将不得不把标签附加到已经存在于 DOM 中的一个 HTML 元素上。例如，头部元素。

**语法:**

```tshtml
const node = document.createElement('script');
node.src = 'SCRIPT_FILE_OR_URL_HERE'
node.type = 'text/javascript';
document.getElementsByTagName('head')[0].appendChild(node);

```

**示例 1:** 在本例中，我们在组件加载时动态地从文件系统加载一个`load.js`文件。

## app.component.html

```tshtml
<div style="text-align:center;">
    <h1 style="color: green;">
        GeeksForGeeks
    </h1>
</div>
```

## app.component.ts

```tshtml
import { Component } from '@angular/core';

@Component({
   selector: 'app-root',
   templateUrl: './app.component.html',
   styleUrls: ['./app.component.css']
})
export class AppComponent {
   title = 'Load script GFG';
   constructor() {
     this.loadScripts();
   }

   // Method to dynamically load JavaScript
   loadScripts() {

     // This array contains all the files/CDNs
     const dynamicScripts = [
        'assets/load.js'
     ];
     for (let i = 0; i < dynamicScripts.length; i++) {
       const node = document.createElement('script');
       node.src = dynamicScripts[i];
       node.type = 'text/javascript';
       node.async = false;
       document.getElementsByTagName('head')[0].appendChild(node);
     }
  }
}
```

## load.js

```tshtml
alert('load js has been loaded'); 
```

**输出:**app . component 一加载，脚本也会加载并显示警报窗口。
T3】

**示例 2:** 在本例中，我们将在按钮点击时加载`load.js`脚本。

## app.component.html

```tshtml
<div style="text-align:center;">
    <h1 style="color: green;">
        GeeksForGeeks
    </h1>
    <button (click)="loadScripts($event)">
        Click me to load JS
    </button>
</div>
```

## app.component.ts

```tshtml
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Load script GFG';
  constructor() {
  }
  loadScripts($event) {
    const dynamicScripts = [
      'assets/load.js'
    ];
    for (let i = 0; i < dynamicScripts.length; i++) {
      const node = document.createElement('script');
      node.src = dynamicScripts[i];
      node.type = 'text/javascript';
      node.async = false;
      document.getElementsByTagName('head')[0].appendChild(node);
    }
  }
}
```

## load.js

```tshtml
alert('load js has been loaded'); 
```

**输出:**按下按钮，加载 JS 文件。
T3】