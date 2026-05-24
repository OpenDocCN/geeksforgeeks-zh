# 如何在 Angular 10 中检查窗体或控件是否未被触及？

> 原文:[https://www . geeksforgeeks . org/如何检查表单或控件是否未被触及或未处于角度-10/](https://www.geeksforgeeks.org/how-to-check-whether-a-form-or-a-control-is-untouched-or-not-in-angular-10/)

在本文中，我们将检查 Angular 10 中的表单是否未被修改。**非接触属性**用于报告控件或表单是否有效。

**语法:**

```ts
form.untouched
```

**返回值:**

*   **布尔值:**将布尔值设置为检查表单是否未被修改。

**模块:**未接触属性使用的模块是:

*   模具模块

**进场:**

*   创建要使用的角度应用程序。
*   在 app.component.html，使用表单指令制作表单。
*   在 app.component.ts 中，使用非接触属性获取信息。
*   使用 ng serve 为 angular app 服务，以查看输出。

**例 1:**

## app.component.ts

```ts
import { Component } from '@angular/core';
import { FormGroup, FormControl, FormArray, Validators } 
    from '@angular/forms'

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  form = new FormGroup({
    name: new FormControl(

    ),
    rollno: new FormControl() 
});

get name(): any {
  return this.form.get('name');
}

onSubmit(): void {
  console.log("Form is untouched : ",this.form.untouched);
}
}
```

## app.component.html

```ts
<br>
<form [formGroup]="form" (ngSubmit)="onSubmit()">
    <input formControlName="name" placeholder="Name">
  <br>
  <button type='submit'>Submit</button>
  <br>
  <br>
</form>
```

**输出:**

![](img/8d80d765422b4c9e4904e80b391aa30e.png)

**参考:**[**https://angular . io/API/forms/abstractcontroldirectional #í**](https://angular.io/api/forms/AbstractControlDirective#untouched)