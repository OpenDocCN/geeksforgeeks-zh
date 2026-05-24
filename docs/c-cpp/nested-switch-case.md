# 嵌套开关箱

> 原文:[https://www.geeksforgeeks.org/nested-switch-case/](https://www.geeksforgeeks.org/nested-switch-case/)

**开关情况说明**:

这些语句代替了将一个变量与几个整数值进行比较的长 if 语句

*   switch 语句是一个多路分支语句。它提供了一种简单的方法，可以根据表达式的值将执行分派到代码的不同部分。
*   Switch 是一个控制语句，它允许一个值改变对执行的控制。

![](img/b3ac657711032acba364c8f60f2531f9.png)

**使用开关盒时需要记住的要点**

*   switch 语句中使用的表达式必须具有整数或字符类型，或者是类类型，其中该类具有到整数或字符类型的单一转换函数。
*   一个开关中可以有任意数量的 case 语句。每种情况后面都跟一个要比较的值，后面跟一个冒号。
*   当被打开的变量等于一个事例时，该事例之后的语句将一直执行，直到到达 break 语句。
*   当到达 break 语句时，开关终止，控制流跳到开关语句之后的下一行。
*   不是每个案例都需要包含中断。如果没有中断出现，控制流将进入后续案例，直到达到中断，即一旦编译器发现比较为真，所有案例语句都将被执行。
*   switch 语句可以有一个可选的默认大小写，它必须出现在 switch 的末尾。当所有案例都不成立时，可以使用默认案例来执行任务。默认情况下不需要中断。

**语法:**

```cpp
switch (n)
{
    case 1: // code to be executed if n = 1;
  break;
    case 2: // code to be executed if n = 2;
  break;
    default: // code to be executed if 
      // n doesn't match any cases
}
```

**嵌套开关语句:**

嵌套开关语句是指另一个开关语句内部的开关语句。

**语法:**

```cpp
switch(n)
{
  // code to be executed if n = 1;
  case 1: 

  // Nested switch
  switch(num) 
  {
    // code to be executed if num = 10
    case 10: 
      statement 1;
      break;

    // code to be executed if num = 20
    case 20: 
      statement 2;
      break;

    // code to be executed if num = 30
    case 30: 
      statement 3;
      break;

      // code to be executed if num 
      // doesn't match any cases
      default: 
  } 

  break;

  // code to be executed if n = 2;
  case 2:
    statement 2;
    break;

  // code to be executed if n = 3;
  case 3: 
    statement 3;
    break;

   // code to be executed if n doesn't match any cases
   default: 
}

```

**示例:**

```cpp
// Following is a simple program to demonstrate
// syntax of Nested Switch Statements.
#include <stdio.h>

int main()
{
    int x = 1, y = 2;

    // Outer Switch
    switch (x) {

    // If x == 1
    case 1:

        // Nested Switch

        switch (y) {

        // If y == 2
        case 2:
            printf( "Choice is 2");
            break;

        // If y == 3
        case 3:
            printf( "Choice is 3");
            break;
        }
        break;

    // If x == 4
    case 4:
        printf( "Choice is 4");
        break;

    // If x == 5
    case 5:
        printf( "Choice is 5");
        break;

    default:
        printf( "Choice is other than 1, 2 3, 4, or 5");
        break;
    }
    return 0;
}
```

**Output:**

```cpp
Choice is 2

```