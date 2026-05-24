# c++ 中的嵌套开关语句

> 原文:[https://www.geeksforgeeks.org/nested-switch-statement-in-c/](https://www.geeksforgeeks.org/nested-switch-statement-in-c/)

**开关情况说明**:

这些语句代替了将一个变量与几个整数值进行比较的长 if 语句

*   switch 语句是一个多路分支语句。它提供了一种简单的方法，可以根据表达式的值将执行分派到代码的不同部分。
*   Switch 是一个控制语句，它允许一个值改变对执行的控制。

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

      // code to be executed if n 
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

#include <iostream>
using namespace std;

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
            cout << "Choice is 2";
            break;

        // If y == 3
        case 3:
            cout << "Choice is 3";
            break;
        }
        break;

    // If x == 4
    case 4:
        cout << "Choice is 4";
        break;

    // If x == 5
    case 5:
        cout << "Choice is 5";
        break;

    default:
        cout << "Choice is other than 1, 2 3, 4, or 5";
        break;
    }
    return 0;
}
```

**Output:**

```cpp
Choice is 2

```