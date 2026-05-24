# 解释在 Angular 2

中创建服务的步骤

> 原文:[https://www . geeksforgeeks . org/explain-the-steps-for-create-a-services-in-angular-2/](https://www.geeksforgeeks.org/explain-the-steps-for-creating-a-services-in-angular-2/)

如果你曾经构建过一个组件，你会意识到这个组件包含一个可执行代码，允许你包含任何你想要的功能。组件的任务是启用用户体验，用户体验将与用户交互。该组件将充当业务逻辑和应用程序视图之间的中介。但是，官方的“角度”样式指南指出将组件的逻辑限制在视图所需的范围内。服务应该处理所有其他逻辑。组件代码中的代码主要用于控制和操作用户界面。它应该调用服务来提供与用户界面没有直接关系的功能。因此，如果视图不需要所需的功能，您应该考虑构建一个服务。

服务用于创建可以共享的变量/数据，并且可以在定义它的组件之外使用。服务本质上是一个有特定目标的类。服务可以是应用程序需要的变量、函数或特性。我们经常使用服务来提供独立于组件的功能，在组件之间传输数据或逻辑，或者封装像数据访问这样的外部交互。通过将这些活动从组件转移到服务，代码变得更容易测试、调试和重用。服务是一种可重用的功能，可以由各种组件使用。服务可以用来避免重写相同的代码，它可以只写一次，并注入到使用该特定服务的所有组件中。

有必要有一个单一的服务责任。你不应该只是把你所有的共享功能放在你的应用程序的一个服务中。服务是附加的功能，可以在应用程序需要的时间和地点交付。我们使用 Angular 通过将我们的服务与依赖注入系统集成来实现这一点。为了生成服务，我们可以遵循两种方法:

*   通过手动创建它来执行特定的任务，我们需要设置和配置服务。
*   通过使用 Angular CLI，它将自动为服务设置所有必要的配置。

我们将通过一系列的例子来理解这两种方法。

**方法 1:** 采用人工方式生成服务:

我们将创建服务类，使用装饰器来描述元数据，然后导入我们需要的内容。这些是我们用来手动构建组件和定制管道的相同基本技术。

**语法:**

```ts
import { Injectable } from '@angular/core';  

@Injectable()  

export class ServiceName {  

}
```

让我们看看构建基本服务的代码，该服务的功能是返回某个学院必须提供的课程列表。

**步骤 1:** 创建一个类 CoursesService 并将文件保存为 *courses.service.ts.* 不要忘记导出该类，以便任何组件都可以使用该服务。让我们将 getdata 方法添加到这个类中。

```ts
export class CoursesService {    // SERVICE CLASS

    constructor() { }

    getdata(): string[] {
        return ['C','C++', 'JAVA', 'Python'];
    }
}
```

**步骤 2:** 然后用装饰器装饰服务元数据。我们在创建服务时使用可注射装饰器。因为装饰器是一个函数，所以它应该被一个左括号和右括号包围。

```ts
@Injectable()      // DECORATOR

export class CoursesService {

 constructor() { }

 getdata(): string[] {
   return ['C','C++', 'JAVA', 'Python'];
 }
}
```

**步骤 3:** 确保定义了正确的导入。现在我们的服务课准备好了。

## 课程.服务. ts

```ts
// IMPORT STATEMENT
import { Injectable } from '@angular/core';

@Injectable()

export class CoursesService {

    constructor() { }

    getdata(): string[] {
        return ['C','C++', 'JAVA', 'Python'];
    }
}
```

**第四步:**现在，我们需要注入我们的服务。服务可以通过两种方式注入。

*   **作为全局服务注入:**将服务注入根模块，使其成为全局服务。该模块中的任何组件现在都可以使用该服务。

    ## 

    ```ts
    import { BrowserModule } from "@angular/platform-browser";
    import { NgModule } from "@angular/core";
    import { AppComponent } from "./app.component";
    import { CoursesService } from "src/services/courses.service";

    @NgModule({
      declarations: [AppComponent],
      imports: [BrowserModule],
      providers: [CoursesService], // FOR GLOBAL SERVICE
      bootstrap: [AppComponent],
    })
    export class AppModule {}
    ```

*   **作为本地服务注入:**将服务直接注入组件，作为本地服务注入。

    ## 

    ```ts
    import { Component } from "@angular/core";
    import { CoursesService } from "src/services/courses.service";

    @Component({
      selector: "app-root",
      templateUrl: "./app.component.html",
      styleUrls: ["./app.component.css"],
      providers: [CoursesService], // FOR LOCAL SERVICE
    })
    export class AppComponent {}
    ```

**第五步:**在这一步中，我们需要将服务导入到组件中，并使用方法。

## app.component.ts

```ts
import { Component } from "@angular/core";
import { CoursesService } from "src/services/courses.service";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
  styleUrls: ["./app.component.css"],
})
export class AppComponent {
  courses: string[];

  constructor(private _coursesService: CoursesService) {}

  ngOnInit() {
    this.courses = this._coursesService.getdata();
  }
}
```

**第 6 步:**更新 HTML 组件进行渲染。

## app.component.html

```ts
<h2>Course List</h2>
<p *ngFor="let c of courses">{{ c }}</p>
```

**第七步:**运行*ng service*启动 app。我们将看到如下输出:

![](img/eeb7e8a1bf6272916b121bdfab63f1f6.png)

**方法 2:** 使用 Angular CLI 生成服务。我们将在 Angular CLI 中使用相同的示例来生成服务。

**步骤 1:** 我们将使用 Angular CLI 创建一个服务。建议使用这种方法，因为出错的机会较少。完成这项任务只需要一个命令。我们将遵循以下语法来创建服务。

**语法:**

```ts
ng g service courses
```

它将生成如下服务代码框架:

```ts
import { Injectable } from '@angular/core';  

@Injectable()

export class ServiceName {   
    constructor() { }
}
```

**步骤 2:** 服务创建后，我们必须将其包含在 **app.module.ts** 的提供商中

```ts
providers: [CoursesService],
```

在这里，服务名称的第一个字母应该是大写，后面跟着没有任何空格的服务。

## app.module.ts

```ts
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';
import { CoursesService } from './courses.service';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule],
  providers: [CoursesService], //FOR GLOBAL SERVICE
  bootstrap: [AppComponent]
})
export class AppModule {}
```

**步骤 3:** 在 *app.component.ts 中，*进行以下更改:

在其余必需的导入中导入服务。

```ts
import { CoursesService } from './courses.service';
```

创建任何类型的变量:课程中不提及任何类型。

在构造函数中，定义服务类型的属性

```ts
constructor(private _coursesService: CoursesService) {}
```

另外，创建一个 *ngOnInit* 方法:

```ts
ngOnInit() {
   this.courses = this._coursesService.getdata();
 }
```

完成上述任务后， *app.component.ts* 文件将如下所示:

## app.component.ts

```ts
import { Component } from '@angular/core';
import { CoursesService } from './courses.service';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  courses: string[];

  constructor(private _coursesService: CoursesService) {}

  ngOnInit() {
    this.courses = this._coursesService.getdata();
  }
}
```

**步骤 4:** 在这一步中，我们将把我们的方法添加到服务中。

## 课程.服务. ts

```ts
import { Injectable } from '@angular/core';  

@Injectable()  

export class CoursesService {  

    constructor() { }

    getdata(): string[] {
        return ['C','C++', 'JAVA', 'Python'];
    }
}
```

**第五步:**在*app.component.html*我们将打印课程中存储的数据。

## app.component.html

```ts
<h2>Course List</h2>
<p *ngFor="let c of courses">{{ c }}</p>
```

**第 6 步:**运行 *ng 发球*，将显示以下输出。

![](img/eeb7e8a1bf6272916b121bdfab63f1f6.png)