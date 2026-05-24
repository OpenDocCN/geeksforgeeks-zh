# 【AngularJS 表达式和 JavaScript 表达式的区别

> 原文:[https://www . geesforgeks . org/difference-anglarjs-expressions-and-JavaScript-expressions/](https://www.geeksforgeeks.org/difference-between-angularjs-expressions-and-javascript-expressions/)

**[Angularjs 表达式:](https://www.geeksforgeeks.org/angularjs-expressions/)**Angularjs 中的表达式用于将应用程序数据绑定到 HTML。表达式由 Angular 解析，结果返回到编写表达式的位置。AngularJS 中的表达式是用双大括号写的:{{ expression }}。它们的行为类似于 ng-bind 指令:ng-bind="expression "。

**例:**

```ts
   <div>
        3 +  3= {{3 + 3}} 
        3 - 3 = {{3 - 3}}
        3 * 3 = {{3 * 3}} 
        3 / 3 = {{3 / 3}}
   </div>

```

**JavaScript 表达式:** If 一组有效的**文字**、**变量**、**运算符**，以及计算为单个值的表达式，即表达式。该单个值可以是一个**数字**、一个**字符串**或一个**逻辑值**作为依赖表达式。有了这个概念，有两种表达方式。

*   **Assign a value to a variable:**

    ```ts
    x = 11
    ```

*   **Simply put, there is a value:**

    ```ts
    22 + 11
    ```

**JavaScript 有以下几种表达式:**

*   **Arithmetic:** These are expressions that evaluate to numbers.
*   **Logic:** These are expressions that evaluate to true or false.
*   **String:** These are expressions for calculating strings, such as "geek" or "987".

**注意:**特殊关键字**空**表示空值。

**Angular 表达式和 JavaScript 表达式的区别**

| parameter | 安圭拉菲兰达 | Java Script 语言表达式 |
| context | The Angular expression is evaluated against scopeobject. | Evaluate JavaScript expressions against global windows. |
| forgive | In Angular, expression evaluation is that forgiveness is undefined and invalid. | A JavaScript expression that attempts to evaluate an undefined property will generate a ReferenceError or TypeError. |
| Control flow statement | Control flow statements cannot be used in angularjs expressions, that is, loops, conditions or exceptions. | Control flow statements can be used in JavaScript expressions. |
| Function declaration | Angular expressions do not allow function declarations, even inside the ng-init instruction. | Function declarations are allowed in JavaScript expressions. |
| Bitwise, comma and void operators | Bitwise, or Void operators cannot be used in Angular expressions. | You can use Bitwise, or void operators in JavaScript expressions. |
| filter | Angle expressions can work with filters. | JavaScript expressions do not work with filters. |
| Primary binding | Primary binding is supported by AngularJS. To create a one-time binding, use the:: expression. | JavaScript expressions do not allow binding at once. |