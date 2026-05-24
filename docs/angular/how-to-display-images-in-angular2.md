# 如何在 Angular2 中显示图像？

> 原文:[https://www . geeksforgeeks . org/如何显示成角图像 2/](https://www.geeksforgeeks.org/how-to-display-images-in-angular2/)

我们可以在 angular2 中提供图像，方法是首先将图像放在项目的资产目录中，您可以在其中为图像创建一个特定的目录，或者直接将它保留在资产目录中。
将所有需要的图像放入资产目录后，打开特定的组件类型脚本(。ts)文件，您希望在其中提供图像。现在，您可以将图像的 URL 添加到构造函数中的一个变量中，以便在组件创建时对其进行初始化。

**示例**
**演示。组件**

```tshtml
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-demo',
  templateUrl: './demo.component.html',
  styleUrls: ['./demo.component.css']
})

export class DemoComponent implements OnInit {
  ImagePath: string;

  constructor() {
    //image location
    this.ImagePath = '/assets/images/sample.jpg'
  }

  ngOnInit() {
  }

}
```

现在修改组件的模板文件以获取图像。
**Demo.Component.html**

```tshtml
<!--...header and body content-->

<mat-card class="example-card" >
  <mat-card-header class="example-header" 
                   style="padding-left: 40%;">
   <h2><span></span>GeeksforGeeks</h2  >
  </mat-card-header>
  <mat-card-content>
    <img [src] ="ImagePath" 
          style="width: 600px;height: 400px;">
  </mat-card-content>
</mat-card>

<!--... body and footer content-->
```

**输出:** ![Output image](img/b46c7e66007d775c43fceff529facc89.png)

您也可以直接从网站或数据库中获取网页图像(例如。Firebase)，方法是提供图像的完整有效 URL。

**注意:**
在 angular2 中，默认情况下，图像和其他媒体是从项目文件夹中的资产目录中获取的(默认情况下，项目的所有其他目录对组件都不是公共的)这可以通过修改 **angular-cli.json** 来更改。在这个 JSON 文件中，通过将其添加到**资产**对象属性中来添加您的媒体目录。

```tshtml
//add a new directory or image to start fetching from that location

"assets": [
 "assets",
 "img",
 "favicon.ico",
 ".htaccess"
]
```