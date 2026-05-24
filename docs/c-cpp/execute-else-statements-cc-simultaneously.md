# 同时执行 C/C++ 中的 if 和 else 语句

> 原文:[https://www . geeksforgeeks . org/execute-else-statements-cc-concurrent/](https://www.geeksforgeeks.org/execute-else-statements-cc-simultaneously/)

编写一个同时执行两个 if-else 块语句的 C/C++ 程序。

```cpp
Syntax of if-else statement in C/C++ language is:
if (Boolean expression)
{
    // Statement will execute only 
    // if Boolean expression is true
}
else
{
    // Statement will execute only if 
    // the Boolean expression is false 
}
```

因此，我们可以得出结论，根据布尔表达式的条件，if-else 语句中只有一个块会执行。

但是我们可以更改代码，以便 if 块和 else 块中的语句在相同的条件下执行。

诀窍是使用 goto 语句，该语句提供从“goto”到同一函数中有标签语句的无条件跳转。

下面是同时执行两个语句的 C/C++ 程序:-

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
if (1) // Replace 1 with 0 and see the magic
{
    label_1: cout <<"Hello ";

    // Jump to the else statement after
    // executing the above statement
    goto label_2;
}
else
{
    // Jump to 'if block statement' if
    // the Boolean condition becomes false
    goto label_1;

    label_2: cout <<"Geeks";
}
return 0;
}

// this code is contributed by shivanisinghss2110
```

## C

```cpp
#include <stdio.h>
int main()
{
  if (1) //Replace 1 with 0 and see the magic
  {
    label_1: printf("Hello ");

    // Jump to the else statement after
    // executing the above statement
    goto label_2;
  }
  else
  {
    // Jump to 'if block statement' if
    // the Boolean condition becomes false
    goto label_1;

    label_2: printf("Geeks");
  }
  return 0;
}
```

**输出:**

```cpp
Hello Geeks
```

因此，if 和 else 语句同时执行。*另一个有趣的事实可以看出，输出将始终保持**不变，并且不取决于布尔条件是真还是假。*

**注意**–在任何编程语言中，都非常不鼓励使用 goto 语句，因为它会使程序的控制流难以跟踪，从而使程序难以理解和修改。作为程序员，我们应该避免在 C/C++ 中使用 goto 语句。

本博客由 [Shubham Bansal](https://www.facebook.com/banalshubham) 投稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。