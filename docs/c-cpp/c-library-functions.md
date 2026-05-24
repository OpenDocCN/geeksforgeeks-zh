# C 库函数

> 原文:[https://www.geeksforgeeks.org/c-library-functions/](https://www.geeksforgeeks.org/c-library-functions/)

[C](https://www.geeksforgeeks.org/c-language-set-1-introduction/) 中的标准函数库是一个巨大的子库库，每个子库包含几个[函数](https://www.geeksforgeeks.org/functions-in-c/)的代码。为了利用这些库，通过使用[头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)链接更广泛的库中的每个库。这些函数的定义出现在它们各自的头文件中。为了使用这些[功能](https://www.geeksforgeeks.org/functions-in-c/)，我们必须在程序中包含头文件。下面是一些带有描述的头文件:

<figure class="table">

| 没有。 | header file | describe |
| --- | --- | --- |
| one |  | It checks the value of the expression that we expect to be true under normal circumstances.
If the expression is a non-zero value, the assert macro does not perform any operation. |
| Two |  | A set of functions for manipulating complex numbers. |
| three | <float .="" h=""></float> | Define macro constants and specify the implementation-specific properties of
floating-point library. |
| four |  | These restrictions stipulate that variables cannot store any values beyond these restrictions, for example-
an unsigned character can store up to 255 values. |
| five |  | Math. h header defines various mathematical functions and a macro. All functions
in this library take double as parameter and return double as result. |
| six | <stdio .="" h=""></stdio> | The header of stdio. h defines three variable types, several macros and various
functions for input and output. |
| seven |  | Define date and time processing functions. |
| eight |  | A string is defined as an array of characters. The difference between the character array
and the string is that the string ends with the special character "\0". |

</figure>

**实现:**我们用一个 [C 程序](https://www.geeksforgeeks.org/c/)来讨论一下基础库的实现:

**1。**[**stdio . h**](https://www.geeksforgeeks.org/whats-difference-between-and/)**:**这个库是用来使用 [printf()函数](https://www.geeksforgeeks.org/return-values-of-printf-and-scanf-in-c-cpp/)的，头文件< stdio.h >应该包含在程序中。下面是实现上述方法的 C 程序:

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>

// Driver code
int main()
{
    printf("GEEKS FOR GEEKS");
    return 0;
}
```

**Output**

```cpp
GEEKS FOR GEEKS
```