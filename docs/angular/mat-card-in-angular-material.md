# <mat-card>在</mat-card>角材

> 原文:[https://www.geeksforgeeks.org/mat-card-in-angular-material/](https://www.geeksforgeeks.org/mat-card-in-angular-material/)

Angular Material 是一个 UI 组件库，由 Angular 团队开发，用于构建桌面和移动网络应用程序的设计组件。为了安装它，我们需要在我们的项目中安装 angular，一旦你有了它，你可以输入下面的命令并下载它。

**安装语法:**

```ts
ng add @angular/material
```

**说明:**

**<mat-card>****是一个内容容器****可以用来在主题的上下文中插入文本、照片和动作。**

**在 Angular Material 中<mat-card>有很多属性，我们可以用来构建简单的卡片。这些属性可以很容易地集成，我们可以用一种更简单的方式对卡片进行编码。下表详细列出了所有属性。</mat-card>**

<figure class="table">

| **元素名称** | **元素描述** |
| <mat-card-title></mat-card-title> | 相应卡片的标题 |
| <mat-card-subtitle></mat-card-subtitle> | 相应卡片的副标题 |
| <mat-card-content></mat-card-content> | 作为卡片主体的所有数据和信息都需要写在这一部分。 |
| <mat-card-actions></mat-card-actions> | 该标签用于提及所有要写入卡片的事件，如提交、取消等
。 |
| <mat-card-header></mat-card-header> | 它用于提及卡片标题上的所有细节，如标题、副标题等。 |

</figure>

****进场:****

*   **首先，使用上述命令安装角度材料。**
*   **安装完成后，从 app.module.ts 文件中的“@angular/material/card”导入“MatCardModule”。**
*   **现在使用表中提到的上面的标签，编码一张卡片。**
*   **确保每个标签都出现在开始(<mat-card>)和结束(</mat-card>)标签中。**
*   **如果您正在使用<mat-button>，那么请确保您也正在导入“MatButtonModule”。</mat-button>**
*   **完成上述步骤后，开始项目。**

****代码实现:****

****app.module.ts:****

## **java 描述语言**

```ts
import { NgModule } from '@angular/core'; 
import { BrowserModule } from '@angular/platform-browser'; 
import { FormsModule } from '@angular/forms'; 

import { AppComponent } from './app.component'; 
import { MatCardModule} from '@angular/material/card';  
import { MatButtonModule} from '@angular/material/button';  

@NgModule({ 
  imports: 
  [ BrowserModule,  
    FormsModule,
    MatCardModule,
    MatButtonModule
 ], 
  declarations: [ AppComponent ], 
  bootstrap:    [ AppComponent ] 
}) 
export class AppModule { }
```

****app.component.css:****

**p {font-family: Lato;}

。示例-卡片{
-最大宽度:500px
保证金:4px

mat-card-副标题{
字号:30px
}

mat-card-title{
颜色:绿色；
字号:40px** 

****app.component.html:****

## **超文本标记语言**

```ts
<mat-card class="example-card">
    <mat-card-header>
        <mat-card-title>GeeksForGeeks</mat-card-title>
        <mat-card-subtitle>
            One stop solution for all CS Subjects
        </mat-card-subtitle>
    </mat-card-header>

    <mat-card-content>
        <p>
            With the idea of imparting programming 
            knowledge, Mr. Sandeep Jain, an IIT Roorkee 
            alumnus started a dream, GeeksforGeeks. 
            Whether programming excites you or you feel 
            stifled, wondering how to prepare for 
            interview questions or how to ace data 
            structures and algorithms, GeeksforGeeks 
            is a one-stop solution. With every tick of 
            time, we are adding arrows in our quiver.
            From articles on various computer science 
            subjects to programming problems for practice,
            from basic to premium courses, from technologies
            to entrance examinations, we have been building
            ample content with superior quality. In a short
            span, we have built a community of 1 Million+ 
            Geeks around the world, 20,000+ Contributors and
            500+ Campus Ambassador in various colleges across
            the nation. Our success stories include a lot of
            students who benefitted in their placements and 
            landed jobs at tech giants. Our vision is to 
            build a gigantic network of geeks and we are 
            only a fraction of it yet.
        </p>
    </mat-card-content>

    <mat-card-actions>
        <button mat-button style=
            "background-color:blue; color:white">
            LIKE
        </button>

        <button mat-button style=
            "background-color:green; color:white">
            SHARE
        </button>
    </mat-card-actions>
</mat-card>
```

****app.component.ts:****

## **java 描述语言**

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: [ './app.component.css' ]
})
export class AppComponent  {
}
```

****输出:****

**![](img/e6e78b34956987bbfe6ccce054a758fd.png)**