# C 和 C++ 代码不兼容

> 原文:[https://www . geesforgeks . org/不兼容-c 和-cpp/](https://www.geeksforgeeks.org/incompatibilities-between-c-and-cpp/)

导致大多数实际问题的 C/C++ 不兼容性并不微妙。大多数很容易被编译器捕获。
本节给出了非 C++ 的 C 代码示例:

**1)** 在 C 语言中，可以使用一种语法来定义函数，该语法可以在参数列表之后选择性地指定参数类型:

```cpp
// C code that uses argument types after
// the list of arguments.
#include<stdio.h>
void fun(a, b)int a;int b;     // Invalid in C++
{
    printf("%d %d", a, b);
}

// Driver code
int main()
{
    fun(8, 9);
    return 0;
}
```

```cpp
Output:
8 9 

```

```cpp
Error in C++ :-  a and b was not declared in this scope 
```

**2)** 在 C 和 C++ 的前标准版本中，类型说明符默认为 int。

```cpp
// C code to show implicit int declaration.
#include<stdio.h>
int main()
{
    // implicit int in C, not allowed in C++
    const a = 7;    

    printf("%d", a);
    return 0;
}
```

```cpp
Output:
7

```

```cpp
Error in C++ :-  a does not name a type 
```

**3)** 在 C 语言中，一个全局数据对象可以多次声明，而无需使用**外部**说明符。只要最多有一个这样的声明提供了初始值设定项，对象就被认为只定义了一次。

```cpp
// C code to demonstrate multiple global
// declarations of same variable.
#include<stdio.h>

// Declares single integer a, not allowed in C++
int a;   int a;  
int main()
{
    return 0;
}
```

```cpp
Error in C++ :-  Redefinition of int a
```

**4)** 在 C 语言中，void*可用作任何指针类型变量赋值或初始化的右手操作数。

```cpp
// C code to demonstrate implicit conversion
// of void* to int*
#include<stdio.h>
#include<malloc.h>
void f(int n)
{
    // Implicit conversion of void* to int*
    // Not allowed in C++.
    int* p = malloc(n* sizeof(int));  
}

// Driver code
int main()
{
    f(7);
    return 0;
}
```

```cpp
Error in C++ :-  Invalid conversion of void* to int*
```

**5)** 在 C 语言中，数组可以由初始值设定项初始化，该初始值设定项包含的元素比数组要求的多。

```cpp
// C code to demonstrate that extra character
// check is not done in C.
#include<stdio.h>
int main()
{
    // Error in C++
    char array[5] = "Geeks";      

    printf("%s", array);
    return 0;
}
```

输出:

```cpp
Geeks

```

```cpp
Error in C++ :-  Initializer-string for array of chars is too long
```

**6)** 在 C 语言中，一个没有指定任何参数类型的函数可以接受任意数量的任何类型的参数。点击[这里](https://www.geeksforgeeks.org/difference-int-main-int-mainvoid/)了解更多。

```cpp
// In C, empty brackets mean any number
// of arguments can be passed
#include<stdio.h>

void fun() {  } 
int main(void)
{
    fun(10, "GfG", "GQ");  
    return 0;
}
```

```cpp
Error in C++ :-  Too many arguments to function 'void fun()'
```

**相关文章:**

*   [C/c++ 写“void main()”或者“main()”可以吗？](https://www.geeksforgeeks.org/fine-write-void-main-cc/)
*   [C/c++ 中“int main()”和“int main(void)”的区别？](https://www.geeksforgeeks.org/difference-int-main-int-mainvoid/)
*   [c++ 程序输出|第 24 集(C++ vs C)](https://www.geeksforgeeks.org/output-c-programs-set-24-c-vs-c/)

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。