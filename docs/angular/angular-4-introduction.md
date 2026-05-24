# 棱角分明 4 |简介

> 原文:[https://www.geeksforgeeks.org/angular-4-introduction/](https://www.geeksforgeeks.org/angular-4-introduction/)

**Angular 4** 在 AngularJS 正式发布 5 年后发布。在这两个版本之间，引入了 Angular 2，这是对 AngularJS 的完全重写。AngularJS 的“MVC”架构被抛弃了，在 Angular 2 中引入了一个新的“服务控制器”架构。在 Angular 2 之后是 Angular 4，它比它的前身效率更高。然而，两个版本中使用的架构是相同的，因此将项目从 v2 升级到 v4 相对比从 JS 升级到 v2 更容易。
Angular 3 被跳过，因为路由器包已经在 3.3.0 版本中。为了避免任何进一步的故障，团队决定跳过 v3.x，将所有其他模块直接升级到 v 4.0。angular 4 最初于 2017 年 3 月发布。

**特征:**

*   **架构:**AngularJS 的 MVC 架构被‘服务控制器’架构取代。
*   **视图引擎:**视图引擎有助于将组件代码减少 60%。这使得应用程序很轻，因为包的大小减少了几千字节。
*   **动画:**动画现在有一个单独的包。动画也可以从*@ angular/platform-browser/动画*的*浏览器导入。*
*   **Typescript:** Angular 4 使用 Typescript v2.2，Typescript 被认为是 Javascript 的超集。
*   **新关键词:**引入了‘as’等新关键词。这通常用于将切片或命令的输出存储在某个变量中。“否则”条件也在 Angular 4 中引入。“如果-否则”的引入；循环条件有助于代码浓缩。
    *   **使用‘as’关键字:**

        ```ts
        <div *ngFor="let j of weeks | slice:0:5 as num">
           Months: {{j}} Num: {{num.length}}
        </div>
        ```

    *   **在角度 4 中使用“if-else”条件:**ngIf 输出“有效条件”，而“else”条件输出“无效条件”。

        ```ts
        <span *ngIf="isavailable; else condition1">
        Valid Condition.</span>
        <ng-template #condition1>
        Invalid Condition</ng-template>
        ```

*   **移动支持:** Angular 4 几乎每个现代的移动浏览器都支持。
*   **HTTP 搜索参数:**不需要为 HTTP 搜索参数调用 URLSearchParams。
*   **与上一版本兼容:** Angular 4 兼容 Angular 2 和 AngularJS。在 Angular 2 中开发的项目将在 Angular 4 中毫无问题地工作。