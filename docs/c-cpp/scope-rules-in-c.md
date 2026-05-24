# C

中的范围规则

> 原文:[https://www.geeksforgeeks.org/scope-rules-in-c/](https://www.geeksforgeeks.org/scope-rules-in-c/)

标识符的作用域是程序中标识符可以直接访问的部分。在 C 语言中，所有标识符都是[词汇(或静态)范围的](https://www.geeksforgeeks.org/static-and-dynamic-scoping/)。c 范围规则可分为以下两类。

基本上有 4 个范围规则:

<figure class="table">

| range | meaning |
| --- | --- |
| File range | An identifier ranges from the beginning of the file to the end of the file. It only refers to those identifiers declared outside all functions. The identifier of the file range is visible throughout the file, and the identifier with the file range is global. |
| Block range | The range of identifiers starts at the beginning of block/"{"and ends at the end of block/"}". An identifier with a block range is local to its block. |
| Function prototype range | Identifiers declared in a function prototype are visible in the prototype. |
| Function range | The function range starts at the beginning of the function and ends at the end of the function. The functional scope only applies to labels. The declared tag is used as the target of goto statement, and goto and tag statement must be in the same function. |

</figure>

让我们用例子来讨论每个范围规则。

**文件范围:**这些变量通常在所有函数和块之外声明，在程序的顶部，可以从程序的任何部分访问。这些变量也称为全局范围变量，因为它们可以被全局访问。

**例 1:**

## C

```cpp
// C program to illustrate the global scope

#include <stdio.h>

// Global variable
int global = 5;

// global variable accessed from
// within a function
void display()
{
    printf("%d\n", global);
}

// main function
int main()
{
    printf("Before change within main: ");
    display();

    // changing value of global
    // variable from main function
    printf("After change within main: ");
    global = 10;
    display();
}
```

**输出:**

```cpp
Before change within main: 5
After change within main: 10
```

**例 2:**

## C

```cpp
// filename: file1.c

int a;

int main(void)
{
   a = 2;
}
```

## C

```cpp
// filename: file2.c
// When this file is linked with file1.c, functions
// of this file can access a

extern int a;

int myfun()
{
   a = 2;
}
```

*注意:*要限制只能访问当前文件，全局变量可以标记为静态。

**Block 作用域:**Block 是包含在左右大括号内的一组语句，即“{”和“}”。块可以嵌套在 C 语言中(一个块可能包含其他块)。在块内声明的变量可以在该块和该块的所有内部块中访问，但不能在块外访问。基本上，这些是定义变量的块的本地变量，不能从外部访问。

## C

```cpp
#include <stdio.h>

// Driver Code
int main()
{
    {
        int x = 10, y = 20;
        {
            // The outer block contains
            // declaration of x and
            // y, so following statement
            // is valid and prints
            // 10 and 20
            printf("x = %d, y = %d\n", x, y);
            {
                // y is declared again,
                // so outer block y is
                // not accessible in this block
                int y = 40;

                // Changes the outer block
                // variable x to 11
                x++ ;

                // Changes this block's
                // variable y to 41
                y++ ;

                printf("x = %d, y = %d\n", x, y);
            }

            // This statement accesses
            // only outer block's
            // variables
            printf("x = %d, y = %d\n", x, y);
        }
    }
    return 0;
}
```

**输出:**

```cpp
x = 10, y = 20
x = 11, y = 41
x = 11, y = 20
```

**功能原型范围:**这些变量范围包括在功能参数列表中。这些变量的作用域从函数原型中的声明之后开始，一直到声明列表的末尾。这些范围不包括函数定义，而只包括函数原型。

**示例:**

## C

```cpp
// C program to illustrate
// function prototype scope

#include <stdio.h>

// function prototype scope
//(not part of a function definition)
int Sub(int num1, int num2);

// file scope
int num1;

// Function to subtract
int Sub(int num1, int num2)
{
    return (num1-num2);
}

// Driver method
int main(void)
{
    printf("%d\n", Sub(10,5));
    return 0;
}
```

**输出:**

```cpp
5
```

**功能范围:**功能范围从功能打开开始，到功能关闭结束。功能范围仅适用于标签。声明的标签用作转到语句的目标，go to 和 label 语句必须在同一个函数中。

**示例:**

## C

```cpp
void func1()
{
    {
        // label in scope even
        // though declared later
        goto label_exec;

    label_exec:;
    }

    // label ignores block scope
    goto label_exec;
}

void funct2()
{

    // throwserror:
    // as label is in func1() not funct2()
    goto label_exec;
}
```

现在，关于变量的访问范围可能会出现各种问题:

**如果内部块本身有一个同名的变量呢？**
如果一个内部块声明了一个与外部块声明的变量同名的变量，那么外部块变量的可见性在内部块声明的点结束。

**传递给函数的函数和参数怎么办？**
一个函数本身就是一个块。函数的参数和其他局部变量遵循相同的块范围规则。

**该块的变量是否可以在后续的另一个块中访问？**
不，块中声明的变量只能在块内部和该块的所有内部块中访问。

**例如**，以下程序产生编译器错误。

## C

```cpp
int main()
{
  {
      int x = 10;
  }
  {
      // Error: x is not accessible here
      printf("%d", x); 
  }
  return 0;
}
```

**错误:**

```cpp
prog.c: In function 'main':
prog.c:8:15: error: 'x' undeclared (first use in this function)
  printf("%d", x); // Error: x is not accessible here
               ^
prog.c:8:15: note: each undeclared identifier is 
reported only once for each function it appears in
```

**示例:**

## C

```cpp
// C program to illustrate scope of variables

#include<stdio.h>

int main()
{
    // Initialization of local variables
    int x = 1, y = 2, z = 3;

    printf("x = %d, y = %d, z = %d\n",
    x, y, z);
    {

        // changing the variables x & y
        int x = 10;
        float y = 20;

        printf("x = %d, y = %f, z = %d\n",
        x, y, z);
        {

            // changing z
            int z = 100;
            printf("x = %d, y = %f, z = %d\n",
            x, y, z);
        }
    }
    return 0;
}
```

**输出:**

```cpp
x = 1, y = 2, z = 3
x = 10, y = 20.000000, z = 3 
x = 10, y = 20.000000, z = 100
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。