# 在 Angular 10

中显示或隐藏子组件

> 原文:[https://www . geesforgeks . org/show-or-hide-children-in-angular-10/](https://www.geeksforgeeks.org/show-or-hide-children-components-in-angular-10/)

**先决条件:**必须安装[角](https://www.geeksforgeeks.org/angular-8-introduction/)

在本文中，我们将看到如何在 Angular 中显示或隐藏子组件。

*   Let's start by creating a new project. Create a new folder and initialize a new angle project. Run the project to verify that it is working properly.

```ts
ng new myProject
ng serve -o  
```

*   This will create a new project in the current directory. Now, we can clear the app.component.html file and create a subcomponent to show how to show or hide it.

```ts
ng generate component comp1  
```

*   Now the setup section ends. Let's add this component to our app.component.html file:

```ts
<app-comp1></app-comp1>  
```

*   We will create a button to show and hide components. Let's add the button code to the app.component.html file.

```ts
<button type="button" (click)="showhideUtility()">
    {{buttonTitle}}
</button>  
```

*   ShowhideUtility () here is a method, and buttonTitle is a variable, which we need to define in the app.component.ts file.

## app . component . ts

```ts
import { Component } from '@angular/core';
@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
   export class AppComponent {
   title = 'myProject';
   buttonTitle:string = "Hide";
   showhideUtility(){
   }
}
```

*   Our subcomponents are still blank, so let's add some content. Go to comp1.component.css and add the following code:

## 

```ts
<div>
   This is the Child Component
</div>
```

*   And add some css in comp1.component.css to get a beautiful view:

```ts
div{
height:200px;
width: 200px;
border: 2px lightblue solid;
border-radius: 10px;
background-color: lightgreen;
}
```

*   Now back to app.component.ts, add a new attribute "visible", which will be a Boolean variable to define the display/hide state. When the user triggers the show hide method, it should flip the value of the "visible" variable. So finally, our app.component.ts will look like this:

## app . component . ts

```ts
import { Component } from '@angular/core';
@Component({
 selector: 'app-root',
 templateUrl: './app.component.html',
 styleUrls: ['./app.component.css']
})
export class AppComponent {
 title = 'myProject';
 buttonTitle:string = "Hide";
 visible:boolean = true;
 showhideUtility(){
   this.visible = this.visible?false:true;
   this.buttonTitle = this.visible?"Hide":"Show";
 }
}
```