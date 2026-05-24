# 角度 9/10/11 中的授权保护装置

> 原文:[https://www . geesforgeks . org/auth-guards-in-angular-9-10-11/](https://www.geeksforgeeks.org/auth-guards-in-angular-9-10-11/)

AuthGuard 用于保护路由，防止未经授权的访问。

【AuthGuard 是如何工作的？

Auth guard 提供名为 canActivate 生命周期事件。canActivate 就像一个构造函数。它将在访问路由之前被调用。canActivate 必须返回 true 才能访问该页面。如果返回 false，我们将无法访问该页面。我们可以在 canActivate 函数中编写用户授权和认证逻辑。

> autoguard 用于保护路由免受未经授权的访问

因此，我们在 angular 中创建了一个 AuthGuard，它将保护我们的路由免受未经授权的访问。

**示例:**我们可以通过使用 CLI 运行简单命令来创建 AuthGuard。

> 警卫服务/认证

上面的命令在服务文件夹中创建了 AuthGuard，AuthGuard 的名称是 auth。

## auth.guards.ts

```ts
import { Injectable } from "@angular/core";
import {
    ActivatedRouteSnapshot,
    CanActivate,
    Router,
    RouterStateSnapshot,
    UrlTree
} from "@angular/router";
import { AuthService } from "./auth.service";

@Injectable()
export class AuthGuard implements CanActivate {
    constructor(
        private authService: AuthService,
        private router: Router) { }
    canActivate(
        route: ActivatedRouteSnapshot,
        state: RouterStateSnapshot): boolean | Promise<boolean> {
        var isAuthenticated = this.authService.getAuthStatus();
        if (!isAuthenticated) {
            this.router.navigate(['/login']);
        }
        return isAuthenticated;
    }
}
```

在 canActivate 函数中，我们正在检查用户是否经过身份验证，“getAuthStatus”方法返回一个布尔值。所以基于这个值，我们从 canActivate 方法返回这个值。如果“getAuthStatus”返回值表示用户已经过身份验证，那么我们允许用户访问该页面，否则我们将用户导航到登录页面。

然后我们必须更新我们的路由文件，这样哪个路由受 AuthGuard 保护，哪个路由每个用户都可以访问。

## app-routing.module.ts

```ts
import { NgModule } from '@angular/core';
import { Routes, RouterModule } 
from '@angular/router';
import { AuthGuard } 
from './services/auth.guards';
import { LoginComponent } 
from './auth/login/login.component';
import { SignupComponent } 
from './auth/signup/signup.component';
import { PostCreateComponent } 
from './posts/post-create/post-create.component';
import { PostListComponent } 
from './posts/post-list/post-list.component';

const routes: Routes = [
  { path: '', 
  component: PostListComponent },
  { path: 'create', 
  component: PostCreateComponent, 
  canActivate: [AuthGuard]},
  { path: 'edit', 
  component: PostCreateComponent, 
  canActivate: [AuthGuard] },
  { path: 'login', 
  component: LoginComponent },
  { path: 'signup', 
  component: SignupComponent }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
  providers: [AuthGuard]
})

export class AppRoutingModule { }
```

在路由数组中，我们提供了 canActivate: [AuthGuard]来“创建”和“编辑”路由，因此这两条路由只允许经过身份验证的用户访问，其他路由对所有用户开放。

> {路径:“创建”，组件:PostCreateComponent，canActivate: [AuthGuard]}，
> {路径:“编辑”，组件:PostCreateComponent，canActivate: [AuthGuard] }，

请确保在此路由文件中导入 AuthGuard，并将其添加到@NgModule 提供程序中。

> @NgModule({
> 导入:[RouterModule.forRoot(routes)]，
> 导出:[RouterModule]，
> 提供程序:[AuthGuard]
> })

这就是我们如何在 AngularJS 中保护路由免受未经授权的访问。