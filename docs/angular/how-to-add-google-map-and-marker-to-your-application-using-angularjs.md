# 如何使用 AngularJS 将谷歌地图和标记添加到您的应用程序中？

> 原文:[https://www . geeksforgeeks . org/如何使用 angularjs 将谷歌地图和标记添加到您的应用程序/](https://www.geeksforgeeks.org/how-to-add-google-map-and-marker-to-your-application-using-angularjs/)

目标是在角度应用程序中添加谷歌地图和标记。当用户点击地图上的特定位置时，标记将被添加到该特定位置。为了达到这个目标，我们将使用 AGM(谷歌地图角度)及其组件，这将使解决方案非常容易。

**什么是 Angular 谷歌地图(AGM)？**
AngularJS 提供了 Angular 谷歌地图组件，用于在应用程序中集成谷歌地图服务。AGM 具有可直接用于应用的组件。

**方法和解决方案:**使用角度谷歌地图的步骤如下:

*   使用以下命令将 AGM 安装到您的本地角度项目。

    ```ts
    npm install @agm/core --save
    ```

*   生成一个使用服务的应用编程接口密钥。
    *   转到[https://developers . Google . com/maps/documentation/JavaScript/get-api-key](https://developers.google.com/maps/documentation/javascript/get-api-key)并按照所有步骤创建一个 API 密钥。
    *   确保您的应用编程接口已启用，要启用您的应用编程接口，请按照此链接[https://support.google.com/googleapi/answer/6158841?hl=en](https://support.google.com/googleapi/answer/6158841?hl=en)中的步骤操作
*   Import **AgmCoreModule** to your applications

    ```ts
    import { AgmCoreModule } from '@agm/core';
    ```

    在必须将创建的应用编程接口密钥放入 apiKey (apiKey:“这里是您的应用编程接口密钥”)的地方添加 AgmCoreModule.forRoot。

    ```ts
    imports: [
        AgmCoreModule.forRoot({
          apiKey:"your API key here"
        })
    ]

    ```

    **app.module.ts:**

    ```ts
    import { BrowserModule } from '@angular/platform-browser';
    import { NgModule } from '@angular/core';
    import { AgmCoreModule } from '@agm/core';
    import { AppRoutingModule } from './app-routing.module';
    import { AppComponent } from './app.component';

    @NgModule({
      declarations: [
        AppComponent
      ],
      imports: [
        BrowserModule,
        AppRoutingModule,
        AgmCoreModule.forRoot({
          apiKey:"your API Key"
        })
      ],
      providers: [],
      bootstrap: [AppComponent]
    })
    export class AppModule { }
    ```

*   In HTML file component selector **agm-map** is used to introduce map where **latitude** and **longitude** is bind to variables **latitude** and **longitude**. The click on map i.e. **(mapClick)** event is used to pass event with function that contains **lat**and **lng** coordinates of click on the map.

    对于标记**agm-标记**选择器用于相同纬度和经度绑定到局部变量的地方。
    T3

    ```ts
    <agm-map [latitude]="latitude" [longitude]="longitude" 
          (mapClick)="location($event)">
      <agm-marker [latitude]="latitude" [longitude]="longitude">
    </agm-marker>
    </agm-map>
    ```

*   在 TypeScript 文件中，定义了获取坐标并将其绑定到局部变量的函数，该变量用于在单击地图时设置标记。
    T2T4

    ```ts
    import { Component } from '@angular/core';

    @Component({
      selector: 'app-root',
      templateUrl: './app.component.html',
      styleUrls: ['./app.component.css']
    })
    export class AppComponent {
      latitude=51.678418;
      longitude=7.809007;
      location(x){
        this.latitude=x.coords.lat;
        this.longitude=x.coords.lng;
      }
    }
    ```

    T5】

**输出:**运行开发服务器获取地图，点击地图将标记添加到想要的位置。
T3】