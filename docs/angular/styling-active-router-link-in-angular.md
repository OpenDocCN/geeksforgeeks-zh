# 在角度方向上设计活动路由器链路

> 原文:[https://www . geesforgeks . org/styling-active-router-link-in-angular/](https://www.geeksforgeeks.org/styling-active-router-link-in-angular/)

在角度上设置活动路由器链路的样式允许用户区分活动路由器链路和非活动路由器链路。Angular 提供了一种特殊的机制来处理活动的路由器链路。

**进场:**

*   创建要使用的角度应用程序。
*   创建包含导航链接的标题组件。
*   然后在每个路由器链接上应用**“路由器链接活动”**，并为该属性提供 CSS 类。这里我们已经在 CSS 文件中创建了**“活动”**类。
*   向根路由提供 **{确切:真}** ，以避免多个活动路由器链路。

**语法:**

```ts
<a routerLink="/" routerLinkActive="active" >Home</a>
```

**示例:**我们已经创建了带有指定路线的标题组件。

## header.component.html

```ts
<span>
    <ul>
        <li><a routerLink="/" routerLinkActive="active">
            Home
        </a></li>
        <li><a routerLink="/products" 
            routerLinkActive="active">Products
        </a></li>
        <li><a routerLink="/about" 
            routerLinkActive="active">About Us
        </a></li>
        <li><a routerLink="/contact" 
            routerLinkActive="active">Contact Us
        </a></li>
    </ul>
</span>
<router-outlet></router-outlet>
```

这里我们提供了**“routerlink active”**，它是自动激活当前路由的路由功能，我们还必须提供 CSS 类。在**路线中，激活的是一个自动应用于激活路线的 CSS 类。**

## header.component.css

```ts
.active{
    background: 'white'
}
```

但是在这里，它仍然会导致一个问题，我们的主路径总是活动的，即使我们导航到其他路径，这背后的原因是*“路由链接活动”*的工作方式。家庭路由在*“本地主机:4200/”*上工作，其他路由是*“本地主机:4200/关于”*所以*“路由器链接活动”*会在每隔一条路由内找到*“本地主机:4200/”*，并且家庭路由器链接总是活动的，以处理这个角度提供另一个称为路由器链接活动选项的指令。

**更新**

## header.component.htm

```ts
<span>
    <ul>
        <li><a routerLink="/" routerLinkActive="active" 
            [routerLinkActiveOptions]={exact:true}>Home
        </a></li>
        <li><a routerLink="/products" 
            routerLinkActive="active">Products
        </a></li>
        <li><a routerLink="/about" 
            routerLinkActive="active">About Us
        </a></li>
        <li><a routerLink="/contact" 
            routerLinkActive="active">Contact Us
        </a></li>
    </ul>
</span>
<router-outlet></router-outlet>
```

因此*路由链接活动选项*只允许精确的路径匹配作为主组件的活动路由。

**输出:**

![](img/5d7b8580333abe624fdd1fb30ca059ed.png)