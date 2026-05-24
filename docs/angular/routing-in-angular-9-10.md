# 在角度 9/10 处布线

> 原文:[https://www.geeksforgeeks.org/routing-in-angular-9-10/](https://www.geeksforgeeks.org/routing-in-angular-9-10/)

**在 Angular 中路由**允许用户创建具有多个视图的单页应用程序，并允许在它们之间导航。用户可以在这些视图之间切换，而不会丢失应用程序状态和属性。

**进场:**

*   创建要使用的 Angular 应用程序。
*   在应用程序组件内创建导航链接，然后向每条路线提供*“路线链接”*指令，并将路线值传递给*“路线链接”*指令。
*   然后将路由添加到 routing.module.ts 文件，然后将 routing.module.ts 导入 app.module.ts 文件。

**语法:**

*   **HTML:**

```ts
<li><a routerLink="/about" >About Us</a></li>
<router-outlet></router-outlet>
```

*   ts:

```ts
 { path: 'about', component: AboutComponent }
```

**示例:**我们将创建一个使用角度路由的简单角度应用程序。首先，我们通过在命令行界面中运行下面的命令来创建一个 Angular 应用程序。

```ts
ng new learn-routing
```

然后，我们创建了简单的导航，允许我们在不同的组件之间导航，我们还创建了一些组件，因此用户可以使用路由在这些组件之间切换。

## app.component.html

```ts
<span>
    <ul>
        <li><a routerLink="/" >Home</a></li>
        <li><a routerLink="/products" >Products</a></li>
        <li><a routerLink="/about" >About Us</a></li>
        <li><a routerLink="/contact" >Contact Us</a></li>
    </ul>
</span>
<router-outlet></router-outlet>
```

这里，路由器出口是路由器用来标记应该插入模板、匹配组件的路由功能。

然后在 *app-routing.module.ts* 文件里面，我们提供了这些路线，让 angular 知道这些路线。

## app-routing.module.ts

```ts
import { NgModule } from '@angular/core';
import { Routes, RouterModule } from '@angular/router';
import { HomeComponent } from './home.component'
import { ProductComponent } from './product.component'
import { AboutComponent } from './about.component'
import { ContactComponent } from './contact.component'

const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'products', component: ProductComponent },
  { path: 'about', component: AboutComponent },
  { path: 'contact', component: ContactComponent, },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
  providers: []
})
export class AppRoutingModule { }
```

然后只需在 *@NgModule* 导入的 app/module.ts 文件中导入*【分配】*模块。

## app.module.ts

```ts
import { NgModule } from '@angular/core';
import { HomeComponent } from './home.component'
import { ProductComponent } from './product.component'
import { AboutComponent } from './about.component'
import { ContactComponent } from './contact.component'
import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent,
    HomeComponent,
    ProductComponent,
    AboutComponent,
    ContactComponent
  ],
  imports: [
    AppRoutingModule,
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

所以现在在 CLI 中使用*“ng serve”*运行这个，并在浏览器中打开 *localhost://4200* 在这里你可以看到你的导航栏，你可以从一个组件导航到另一个组件而不需要页面重载。

**输出:**

![](img/3b6be6947d5a57d7ef6821bd98bcc680.png)