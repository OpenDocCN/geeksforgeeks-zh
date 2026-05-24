# 如何用 HTTP 在 Angular 中用 Observables 检索数据？

> 原文:[https://www . geesforgeks . org/如何使用 http-with-observables-in-angularjs 检索数据/](https://www.geeksforgeeks.org/how-to-retrieve-data-using-http-with-observables-in-angularjs/)

大多数应用程序从后端服务器获取数据。他们需要发出一个 HTTP GET 请求。在本文中，我们将研究发出一个 HTTP 请求，并将结果/响应映射到一个本地数组中。这个数组可以用来显示或过滤我们想要的项目。这里最重要的是使用可观察的。让我们先快速了解一下可观察性。
可观察性很重要，因为它有助于管理异步数据(例如来自后端服务器的数据)。因此，我们可以将可观察性视为一个数组，其中的项目会随着时间异步到达。对于可观察性，我们需要代码中的一个方法来订阅这个可观察性。可观察性由 angular 本身使用，包括 Angular 事件和 angular HTTP 客户端服务，这就是我们在这里讨论可观察性的原因。
重要步骤如下:

1.  使用命令创建服务:ng g s 相册。这里我们将创建一个类 AlbumService。
2.  在 AlbumService 类中创建一个方法，比如 getAllAlbums()，它将使用 Observable 发出 HTTP GET 请求。
3.  将此服务注入到任何想要使用这些方法的组件的构造函数中。例如- AlbumListComponent。
4.  在 AlbumListComponent 类中创建一个方法或使用有角度的生命周期挂钩，它将订阅可观察到的，然后获取接收到的响应。

**创建服务:**T2T4

## java 描述语言

```ts
import { Injectable } from '@angular/core'
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
import { catchError, tap, map } from 'rxjs/operators';
import { IAlbum } from '../model/album';

@Injectable({
  providedIn: 'root'
})
export class AlbumService {
  albums_url: string =
"https://jsonplaceholder.typicode.com/albums";
  constructor(private _http: HttpClient) {}
}
```

将网址存储在一个变量中。现在我们需要 HttpClient 服务来对该 URL 发出 HTTP GET 请求，因此我们必须将其注入构造函数。请确保在相应的模块文件中从@angular/common/http 导入 HttpClientModule。

## java 描述语言

```ts
@NgModule({
  imports: [ BrowserModule,
       FormsModule, HttpClientModule ],
  declarations: [ ... ],
  providers: [ AlbumService ],
  bootstrap:    [ ...]
})
export class AppModule { }
```