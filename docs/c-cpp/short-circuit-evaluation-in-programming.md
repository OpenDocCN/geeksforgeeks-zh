# 编程中的短路评估

> 原文:[https://www . geesforgeks . org/编程中短路评估/](https://www.geeksforgeeks.org/short-circuit-evaluation-in-programming/)

**短路评估:** [短路](https://www.geeksforgeeks.org/short-circuiting-in-c-and-linux/)是一种编程概念，通过该概念，[编译器](https://www.geeksforgeeks.org/introduction-of-compiler-design/)跳过逻辑表达式中某些子表达式的执行或评估。一旦确定了表达式的值，编译器就停止计算其他子表达式。下面是同样的例子:

## C++

```cpp
if (a == b || c == d || e == f) {
    // do_something
}
```

**说明:**在上面的表达式中，如果表达式 **a == b** 为**真**，那么 **c == d** 和 **e == f** 根本不会被求值，因为表达式的结果已经确定了。同样，如果 [**逻辑 AND ( & &)运算符**](https://www.geeksforgeeks.org/operators-in-c-set-2-relational-and-logical-operators/) 代替**逻辑 OR (||)** ，表达式 **a == b** 为**假**，编译器将跳过对其他子表达式的求值。

**例 1:**

## C++

```cpp
// C program to illustrate the concept
// of short circuiting
#include <stdio.h>

// Driver Code
int main()
{
    int x = 1;

    if (x || ++ x) {
        printf("%d", x);
    }

    return 0;
}
```

**Output**

```cpp
1
```

**解释:**在上面的 [C 程序](https://www.geeksforgeeks.org/c/)中，在 if 语句内部，第一个子表达式即 x 的值是 1(在 boolean 中是 true 的意思)，所以第二个子表达式的值不影响表达式的值，因此编译器跳过检查。所以 x 的值不递增。

**例 2:**

## C

```cpp
// C program to illustrate the concept
// of short circuiting
#include <stdio.h>

// Driver Code
int main()
{
    int a = 10;
    int b = -1;

    // Here b == -1 is not evaluated as
    // a != 10 is false
    if (a != 10 && b == -1) {
        printf("I won't be printed!\n");
    }
    else {
        printf("Hello, else block is printed");
    }

    return 0;
}
```

**Output**

```cpp
Hello, else block is printed
```

**说明:**上面的程序打印 **else 块**的输出，因为第一个条件是**假**，足以确定表达式的值，所以第二个条件不计算。

**例 3:** 下面是计算平方根的 C 程序，演示短路评估的概念:

## C

```cpp
// C program to illustrate the concept
// of short circuiting
#include <math.h>
#include <stdio.h>

// Function to calculate  the square root
int calculate_sqrt(int i)
{
    printf("Sqrt of %d: %.2f\n",
           i, sqrt(i));

    return i;
}

// Driver Code
int main()
{
    int a = 15;

    // Here since a is 10, calculate_sqrt
    // function will be called
    if (a >= 10 && calculate_sqrt(a)) {
        printf("I will be printed!\n");
    }

    return 0;
}
```

**Output**

```cpp
Sqrt of 15: 3.87
I will be printed!
```

**说明:**在上述程序中，如果数字小于 10，则不执行[平方根](https://www.geeksforgeeks.org/square-root-of-an-integer/)。因此，对于负数也避免了错误。

**应用:**短路的概念在很多情况下都有帮助。其中一些列举如下:

*   **避免意外行为:**可以用来避免由于第二个参数导致的意外行为。例如:考虑下面的代码片段:

## C

```cpp
// C program to illustrate the concept
// of short circuiting
#include <stdio.h>

// Driver Code
int main()
{
    float nr = 5, dr = 0;
    dr&& printf("a/b = %.2f", nr / dr);
}
```

**Output**

**说明:**由于表达式 **(nr/dr)** 给出了[运行时错误](https://www.geeksforgeeks.org/runtime-errors/)，但由于在运算中加入了表达式 **dr & &，避免的错误为 **dr** 的值为 **0** ，不包括 **(nr/dr)** 的计算。**

*   **避免昂贵的计算:**它有助于避免仅在特定条件下需要执行的昂贵计算。下面是同样的代码片段:

## C

```cpp
int a = 0;

// myfunc(b) will not be called
if (a != 0 && myfunc(b)) {
    // do_something();
}
```

**示例:**在上面的示例中，如果需要对值 **0** 使用 **myfunc()** 进行昂贵的运算，则可以通过使用该概念来避免对非零值进行昂贵的运算。这也可以用在文件处理中，以避免在文件已经处于就绪状态时每次都要准备好文件的昂贵任务

> isfileready()| | getfileready()

**短路评估的优势:**

*   在某些情况下，它有助于避免计算开销大的任务。
*   它为第一个参数提供检查，如果没有第二个参数，可能会导致运行时错误。

**短路评估的缺点:**

*   如果使用不当，可能会导致意外行为。对于代码片段中任何进行某种系统资源分配/内存分配的[函数](https://www.geeksforgeeks.org/functions-in-c/)，我们可能会得到意想不到的行为。
*   短路执行路径会降低代码执行的效率，因为在某些编译器中，新的短路检查本身就是额外的执行周期。