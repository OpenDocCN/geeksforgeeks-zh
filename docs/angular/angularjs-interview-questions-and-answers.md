# AngularJS 面试问答

> 原文:[https://www . geesforgeks . org/angular js-面试-问答/](https://www.geeksforgeeks.org/angularjs-interview-questions-and-answers/)

![](img/4dfe222d971b935a65fd89aa27f2c8e4.png)

1.  **[What is AngularJS and who created it?](https://www.geeksforgeeks.org/introduction-to-angularjs/)**
    AngularJs is a Javascript open-source front-end framework that is mainly used to develop single-page web applications(SPAs). It is a continuously growing and expanding framework which provides better ways for developing web applications. It changes the static HTML to dynamic HTML. It’s features like dynamic binding and dependency injection eliminates the need for code that we have to write otherwise.AngularJs is rapidly growing and because of this reason, we have different versions of AngularJs with the latest stable being 1.7.7\. It is also important to note that Angular is different from AngularJs. It is an open-source project which can be freely used and changed by anyone. It extends HTML attributes with Directives, and data is bound with HTML.

    AngularJs 最初由 **Misko hevery** 和**Adam abroad**在 2008-2009 年开发，现在由谷歌维护。

2.  **[What are the features of AngularJS?](https://www.geeksforgeeks.org/interesting-facts-and-features-about-angularjs/)**
    There are so many features in AngularJS like MVC Framework, The unique AngularJS Router, User Interface with HTML, Directives, Scope, Data Binding, Dependency Injection, Compability, Avoid Tiresome Work and High Performance.
3.  **Explain what is scope and Data Binding in AngularJS?**
    **[Scope:](https://www.geeksforgeeks.org/angularjs-scope/)** Scope in AngularJS is the binding part of HTML view and JavaScript controller. When you add properties into the scope object in the JavaScript controller, only then the HTML view gets access to those properties. There are two types of Scope in AngularJS.

    **[数据绑定:](https://www.geeksforgeeks.org/angularjs-data-binding/)** Angular 提供了数据绑定功能，帮助我们几乎实时地反映用户给出的输入，即它在模型和视图之间建立了联系。

4.  **[How many types of data bindings are there in AngularJs?](https://www.geeksforgeeks.org/angularjs-data-binding/)**
    There are four kinds of data bindings in AngularJS **Event Binding**, **Property Binding**, **Two way Binding** and **Interpolation Binding**
5.  **Explain the differences between one-way binding and two-way binding.**
    **Property Binding:** Similar to Java, variables defined in the parent class can be inherited by child class that is templates in this case. The only difference between Interpolation and Property binding is that we should not store non-string values in variables while using interpolation. So if we have to store Boolean or other data types than use Property Binding.

    **插值绑定:**角度插值用于使用双花括号语法在相应的视图模板中显示组件属性。插值用于传递组件类中提到的属性，以反映在其模板中。

6.  **Explain the services and expression in AngularJS.**
    **[Services:](https://www.geeksforgeeks.org/angularjs-services/)** Services are used to create variables/data that can be shared and can be used outside the component in which it is defined.
    **[Expression:](https://www.geeksforgeeks.org/angularjs-expressions/)** Expressions in AngularJS are used to bind application data to HTML. The expressions are resolved by Angular and the result is returned back to where the expression is written.
7.  **Explain what is the key difference between angular expressions and JavaScript expressions?**
    AngularJS expression can be written in HTML but JavaScript expression can’t and Filters are supported by AngularJS but not by JavaScript. We cannot use conditional iterations, loops, and exceptions in AngularJs, but we can use all of these conditional properties in JavaScript expressions.
8.  **Write all the steps to configure an Angular App(ng-app)?**
    **Step 1:** The angular.module will be created at first.
    **Step 2:** A controller will be assigned to the module.
    **Step 3:** The module will be linked with the HTML template with an angular app(ng-app).
    **Step 4:** The HTML template will be linked with the controller with an ng-controller directive.
9.  **With options on page load how you can initialize a select box?**
    YOu can initialize a select box using ng-init directive when options on page load.

    ```ts
    <div ng-controller = " apps/dashboard/account " ng-switch
    On = "! ! accounts" ng-init = " loadData ( ) ">
    ```

10.  **[What are Directives in AngularJS and name few of them.](https://www.geeksforgeeks.org/angularjs-directive/)**
    **Directive:** Directives are markers on the DOM element which tell Angular JS to attach a specified behavior to that DOM element or even transform the DOM element with its children. Simple AngularJS allows extending HTML with new attributes called Directives. AngularJS has a set of built-in directives which offers functionality to the applications. It also defines its own directives.
    Popular directives are **ng-app**, **ng-controller**, **ng-bind**, etc.
11.  **What are the advantages of using AngularJS?**
    There are several advantages to AngularJS. Supports the MVC pattern support two ways of data binding using AngularJS. It has per-defined form validations
    Supported both client-server communication and animations.
12.  **[What AngularJS routing does?](https://www.geeksforgeeks.org/angularjs-routing/)**
    Routing in AngularJS is used when the user wants to navigate to different pages in an application but still wants it to be a single page application. AngularJS routes enable the user to create different URLs for different content in an application. The ngRoute module helps in accessing different pages of an application without reloading the entire application.
13.  **How can we share the data between controllers in AngularJS?**
    We have to create a service first. The Services are used to share data between controllers in AngularJS. We use events, $parent, next sibling, and controller by using a $rootScope.
14.  **What are the steps for the compilation process of HTML?**
    **Step 1:** Using the standard browser API, first, the HTML is parsed into DOM
    **Step 2:** By using the call to the $compile() method, a compilation of the DOM is performed. The method traverses the DOM and then matches the directives.
    **Step 3:** Link the template with a scope by calling the linking function returned from the previous step.
15.  **What is string interpolation in AngularJS?**
    In AngularJS, during the compilation process, it matches the text and attributes using interpolate service to see if they contain embedded expressions. As part of the normal digest cycle, these expressions are updated and registered as watches.
16.  **How many types of Directives are available in AngularJS?**
    There are four kinds of directives in AngularJS those are described below:
    *   **元素指令**
    *   **属性指令**
    *   **CSS 类指令**
    *   comment guidelines
17.  **What is injector?**
    The injector in AngularJS is basically a service locator. It is used to invoked methods and for loading modules. There can be only one injector in a single AngularJS app.
18.  **[What is factory method in AngularJS?](https://www.geeksforgeeks.org/angularjs-factory-method/)**
    AngularJS Factory Method makes the development process of AngularJS application more robust. A factory is a simple function that allows us to add some logic to a created object and return the created object. The factory is also used to create/return a function in the form of reusable code which can be used anywhere within the application. Whenever we create an object using a factory it always returns a new instance for that object. The object returned by the factory can be integrated(injectible) with different components of the Angularjs framework such as controller, service, filter or directive.
19.  **What is the digest cycle in AngularJS?**
    It is the most important part of the process of data binding in AngularJS. It basically compares the old and new versions of the scope model. The digest cycle triggered automatically. If we want to trigger the digest cycle manually then we can use $apply().
20.  **[What is the difference between Angular and AngularJS?](https://www.geeksforgeeks.org/difference-between-angular-and-angularjs/)**
    **Angular:** It is written in Microsoft’s TypeScript language, which is a superset of ECMAScript 6 (ES6). In Angular components are the directives with a template. It used Hierarchical Dependency Injection.

    **AngularJS:** 用 JavaScript 写的。支持模型-视图-控制器设计。视图处理模型中可用的信息以生成输出。它不使用依赖注入。