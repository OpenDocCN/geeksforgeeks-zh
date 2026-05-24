# 如何在 Angular 10 中检查窗体或控件是否无效？

> 原文: [https://www.geeksforgeeks.org/how-to-check-whether-a-form-or-a-control-is-invalid-or-not-in-angular-10/](https://www.geeksforgeeks.org/how-to-check-whether-a-form-or-a-control-is-invalid-or-not-in-angular-10/)

在本文中，我们将检查 Angular 10 中的表单是否无效。`invalid` 属性用于报告控件或表单是否无效。

**语法:**

```ts
form.invalid 
```

**返回值:**

*   `Boolean`: 将布尔值设为检查表单是否无效。

**模块:** `invalid` 属性使用的模块是:

*   `FormsModule`

**步骤:**

*   创建要使用的 Angular 应用程序。
*   在 `app.component.html`，使用表单指令制作表单。
*   在 `app.component.ts` 中，使用 `invalid` 属性获取信息。
*   使用 `ng serve` 为 Angular app 服务，以查看输出。

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
    name: new FormControl(),
    rollno: new FormControl() 
});

get name(): any {
  return this.form.get('name');
}

onSubmit(): void {
  console.log("Form is invalid : ",this.form.invalid);
}
}
```

## app.component.html

```ts
<form [formGroup]="form" (ngSubmit)="onSubmit()">
  <input formControlName="name" placeholder="Name">
<br>
<button type='submit'>Submit</button>
<br>
<br>
</form>
```

**输出:**

![](img/b003b79bac84b48bf9f5a025e143901b.png)

**参考:** [https://angular.io/api/forms/AbstractControlDirective#invalid](https://angular.io/api/forms/AbstractControlDirective#invalid)