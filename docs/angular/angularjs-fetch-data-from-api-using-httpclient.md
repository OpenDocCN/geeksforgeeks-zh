# AngularJS |使用 HttpClient 从 API 获取数据

> 原文:[https://www . geesforgeks . org/angular js-fetch-data-from-API-using-httpclient/](https://www.geeksforgeeks.org/angularjs-fetch-data-from-api-using-httpclient/)

应用编程接口中有一些数据，我们在这里的任务是使用 HTTP 从该应用编程接口获取数据并显示它。在本文中，我们将使用一个案例，其中 API 包含我们将获取的员工详细信息。API 是一个假 API，其中数据以 **JSON** (键:值)对的形式存储。
[**API**](https://www.geeksforgeeks.org/introduction-to-apis/)**:**API 代表**应用程序编程接口**，它是一个软件中介，允许两个应用程序相互通信。
Angular 提供 **HttpClient** 在 API 上工作，轻松处理数据。在这种方法中 **HttpClient** 和 **subscribe()方法**将用于获取数据。为了达到解决问题的目的，需要遵循以下步骤。

*   **步骤 1:** 创建必要的组件和应用程序。
*   **步骤 2:** 为**模块中的 **HttpClient** 进行必要的导入。** 

```ts
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  declarations: [
  ],
  imports: [
    HttpClientModule,
  ],
  providers: [],
  bootstrap: []
})
```

*   **步骤 3:** 在 **component.ts** 文件中为 **HttpClient** 做必要的导入。

```ts
import {HttpClient} from '@angular/common/http';

export class ShowApiComponent implements OnInit {
  constructor(private http : HttpClient){

   } 
  }
```

*   **第四步:**我们通过在 **get()方法**中传递 API url，然后订阅该 url，从 API 获取**响应**。

```ts
this.http.get('API url').subscribe(parameter)
```

*   应用编程接口的**响应**存储在一个变量中，从中可以访问数据。
*   **第五步:**现在需要用 HTML 显示数据数组。在表中，行是根据数据数组的大小动态添加的。为此，使用***神经生长因子**创建行，然后显示每行的数据。

**先决条件:**在这里，您需要一个**应用编程接口**来获取数据。还可以创建一个假的 API 并存储数据–“https://www . mocky . io/”。
**示例:**这里举个例子，我们已经有一个包含员工数据的假 API，我们将获取
**API:**http://www . mocky . io/v2/5ea 172973100002d 001 eada】
**显示数据的步骤:**

*   **步骤 1:** 创建所需的角度应用程序和组件(此处显示应用程序组件)
*   **第二步:**对于我们的 app 使用 HttpClient， **HttpClientModule** 导入到**app . module . ts**
    **app . module . ts:**

## java 描述语言

```ts
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { HttpClientModule } from '@angular/common/http';

import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import { AddInputComponent } from './add-input/add-input.component';
import { ShowApiComponent } from './show-api/show-api.component';

@NgModule({
  declarations: [
    AppComponent,
    ShowApiComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    HttpClientModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

*   **第三步:**在组件的 Typescript 文件中(这里显示-api.component.ts)导入 HttpClient。HttpClient 有助于呈现和获取数据。员工详细信息应用编程接口用于获取数据。我们通过在 get()方法中传递 API url，然后订阅该 url，从 API 获得**响应**。应用编程接口的**响应**存储在一个名为 li 的变量中，该变量的数据数组进一步存储在一个名为 list 的数组中。列表数组将帮助我们显示数据。当响应隐藏加载程序时，会调用用户定义的函数。
    **show-app . component . ts:-**T9】

## java 描述语言

```ts
import { Component, OnInit } from '@angular/core';
import {HttpClient} from '@angular/common/http';
@Component({
  selector: 'app-show-api',
  templateUrl: './show-api.component.html',
  styleUrls: ['./show-api.component.css']
})
export class ShowApiComponent implements OnInit {

  li:any;
  lis=[];
  constructor(private http : HttpClient){

}

  ngOnInit(): void {
    this.http.get('http://www.mocky.io/v2/5ea172973100002d001eeada')
    .subscribe(Response => {

      // If response comes hideloader() function is called
      // to hide that loader
      if(Response){ 
        hideloader();
      }
      console.log(Response)
      this.li=Response;
      this.lis=this.li.list;
    });
    function hideloader(){
      document.getElementById('loading').style.display = 'none';}
  }}
// The url of api is passed to get() and then subscribed and
// stored the response to li element data array lis[] is created
// using JSON element property
```

*   **第四步:**现在需要用 HTML 显示数据数组。在表中，行是根据数据数组的大小动态添加的。为此，使用***神经生长因子**创建行，然后显示每行的数据。在这个文件中，我添加了一个加载器，它会加载直到响应到来。
    **show-app . component . html:-**T7】

## 超文本标记语言

```ts
<h1>Registered Employees</h1>
<div class="d-flex justify-content-center">
<div class="spinner-border" role="status" >
    <span class="sr-only" id="loading">Loading...</span>
</div>
</div>
<table class="table" id='tab'>
    <thead>
    <tr>
        <th scope="col">Name</th>
        <th scope="col">Position</th>
        <th scope="col">Office</th>
        <th scope="col">Salary</th>
    </tr>
    </thead>
    <tbody>
    <tr *ngFor="let e of lis;">
        <td>{{ e.name }}</td>
        <td>{{ e.position }}</td>
        <td>{{ e.office }}</td>
        <td>{{ e.salary }}</td>
    </tr>
    </tbody>
</table>                   
```