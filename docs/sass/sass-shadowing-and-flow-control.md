# SASS |阴影和流量控制

> 原文:[https://www . geesforgeks . org/sass-shadowing-and-flow-control/](https://www.geeksforgeeks.org/sass-shadowing-and-flow-control/)

阴影和流量控制是改变[变量](https://www.geeksforgeeks.org/sass-variables/)值的方法。当我们使用 SASS 库时，这两种方法非常有用。我们将逐一讨论。

1.  **Shadowing:**
    Local variables can be declared with the same name as Global variables. If we do that then the value of that variable in the local scope will be the value of the variable in that local scope and not global value. See the example below:

    **SASS 文件:**

    ```html
    $global_local: global-value;

    ul {
        $global_local: local-value;
        width: $global_local; 
    }

    span {
        width: $global_local;
    }

    ```

    **编译后的 CSS 文件:**

    ```html
    ul {
      width: local-value;
    }

    span {
      width: global-value;
    }

    ```

    现在，如果您想在条件执行的某个时刻或出于任何原因更改全局变量的值，该怎么办？SASS 允许我们使用！局部变量声明后的全局。这个概念之所以被称为**‘阴影化’**是因为全局变量值的变化使用了！全局反映在整个文档中，而不仅仅是在！全局表达式。

    **SASS 文件:**

    ```html
    $global_local: global-value;

    ul {
        $global_local: local-value !global;
        width: $global_local; 
    }

    span {
        width: $global_local;
    }

    ```

    **编译后的 CSS 文件:**

    ```html
    ul {
      width: local-value;
    }

    span {
      width: local-value;
    }

    ```

    **注:**！global 只能用于已经声明的变量，否则会在编译时产生错误。

    **用法:**当您使用 SASS 库并且想要更改库中声明的全局变量的值时使用。

2.  **Flow Control:** You can change the value of variables using the flow control compilation. Here the value of the variables will change just after the flow control block. The value of variables before it will remain as it is before. See the example below:

    **SASS 文件:**

    ```html
    // This is default mode
    $background-color-alpha: 0.5;

    @mixin flow-control($dark-mode) {

      // If you want to have dark mode then 
      // use flow-control to make the color dark
      @if $dark-mode {
        $background-color-alpha: 1 !global;
      }

      background-color: rgba(250, 0, 100, $background-color-alpha);
      display: block;
      border-radius: 15px;
      color: white;

    }

    .button {
      @include flow-control(true);
    }

    ```

    **编译后的 CSS 文件:**

    ```html
    .button {
      background-color: #fa0064; // rgba(250, 0, 100, 1);
      display: block;
      border-radius: 15px;
      color: white;
    }

    ```

    **用法:**当我们正在编写自己的 SASS 库，并且希望允许用户通过条件编译来更改我们的全局变量值时，这一点特别有用。