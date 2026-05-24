# C/C++ 中的 pragma 指令

> 原文: [https://www.geeksforgeeks.org/pragma-directive-in-c-c/](https://www.geeksforgeeks.org/pragma-directive-in-c-c/)

该指令是一个特殊目的指令，用于打开或关闭某些功能。这种类型的指令是编译器特定的，即它们因编译器而异。下面讨论一些 `#pragma` 指令:

## 1. `#pragma startup` and `#pragma exit`

这些指令帮助我们指定在程序启动之前（控制权传递给 `main()` 之前）和程序退出之前（控制权从 `main()` 返回之前）需要运行的函数。

**注意**: 下面的程序不会和 GCC 编译器一起工作。

看下面的程序:

```cpp
#include<stdio.h>

void func1();
void func2();

#pragma startup func1
#pragma exit func2

void func1()
{
    printf("Inside func1()\n");
}

void func2()
{
    printf("Inside func2()\n");
}

int main()
{
    printf("Inside main()\n");
    return 0;
}
```

**Output:**

```cpp
Inside func1()
Inside main()
Inside func2()
```

当在 GCC 编译器上运行时，上述代码将产生如下所示的输出:

```cpp
Inside main()
```

出现这种情况是因为 GCC 不支持 `#pragma startup` 或 `#pragma exit`。但是，您可以使用下面的代码在 GCC 编译器上获得类似的输出。

```cpp
#include<stdio.h>

void func1();
void func2();

void __attribute__((constructor)) func1();
void __attribute__((destructor)) func2();

void func1()
{
    printf("Inside func1()\n");
}

void func2()
{
    printf("Inside func2()\n");
}

int main()
{
    printf("Inside main()\n");
    return 0;
}
```

**Output:**

```cpp
Inside func1()
Inside main()
Inside func2()
```

## 2. `#pragma warn` 指令

此指令用于隐藏在编译期间显示的警告消息。当我们有一个大型程序，并且希望在查看警告之前先解决所有错误时，这可能很有用。通过使用它，我们可以通过隐藏所有警告来专注于错误。我们可以通过稍微改变语法再次让警告可见。

**语法**:

```cpp
#pragma warn +xxx (To show the warning)
#pragma warn -xxx (To hide the warning)
#pragma warn .xxx (To toggle between hide and show)
```

我们可以隐藏警告，如下所示:

*   **`#pragma warn -rvl`**: 该指令隐藏了当一个应该返回值的函数没有返回值时发出的警告。
*   **`#pragma warn -par`**: 该指令隐藏了当函数不使用传递给它的参数时发出的警告。
*   **`#pragma warn -rch`**: 该指令隐藏了当代码不可访问时发出的警告。例如: 函数中任何写在 `return` 语句之后的代码都是不可达的。

**例**:

```cpp
// Example to explain the working of
// #pragma warn directive
// This program is compatible with C/C++ compiler

#include<stdio.h>

#pragma warn -rvl /* return value */
#pragma warn -par /* parameter never used */
#pragma warn -rch /*unreachable code */

int show(int x)
{
    // parameter x is never used in
    // the function

    printf("GEEKSFORGEEKS");

    // function does not have a
    // return statement
}

int main()
{
    show(10);
    return 0;
}
```

**Output:**

```cpp
GEEKSFORGEEKS
```

上述程序编译成功，没有任何警告，给出输出“GEEKSFORGEEKS”。

## 3. `#pragma GCC poison`

此指令受 GCC 编译器支持，用于从程序中完全移除一个标识符。如果我们想阻止使用某个标识符，那么我们可以使用 `#pragma GCC poison` 指令。

**例**:

```cpp
// Program to illustrate the
// #pragma GCC poison directive

#include<stdio.h>

#pragma GCC poison printf

int main()
{
    int a=10;

    if(a==10)
    {
        printf("GEEKSFORGEEKS");
    }
    else
        printf("bye");

    return 0;
}
```

上面的程序会给出下面的错误:

```cpp
prog.c: In function 'main':
prog.c:14:9: error: attempt to use poisoned "printf"
         printf("GEEKSFORGEEKS");
         ^
prog.c:17:9: error: attempt to use poisoned "printf"
         printf("bye");
         ^
```

## 4. `#pragma GCC dependency`

`#pragma GCC dependency` 允许您检查当前文件和另一个文件的相对日期。如果另一个文件比当前文件更新，则会发出警告。如果当前文件源自另一个文件并且应该重新生成，这将非常有用。

**语法**:

```cpp
#pragma GCC dependency "parse.y"
#pragma GCC dependency "/usr/include/time.h" rerun fixincludes
```

## 5. `#pragma GCC system_header`

此 `pragma` 不接受任何参数。它导致当前文件中的其余代码被视为来自系统头。

## 6. `#pragma once`

`#pragma once` 指令有一个非常简单的概念。包含此指令的头文件只被包含一次，即使程序员在编译过程中多次包含它。这不包含在任何 ISO C++ 标准中。此指令的工作方式类似于 `#include guard` 惯用法。使用 `#pragma once` 可以使程序免于多重包含优化。

**语法:**

```cpp
#pragma once
```