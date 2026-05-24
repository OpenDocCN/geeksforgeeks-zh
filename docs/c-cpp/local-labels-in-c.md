# C 中的本地标签

> 原文:[https://www.geeksforgeeks.org/local-labels-in-c/](https://www.geeksforgeeks.org/local-labels-in-c/)

每个用 C 编程语言编程的人都必须知道在 C 中使用的“goto”和“labels”，以便在 C 函数中跳转。GCC 为 C 提供了一个称为“本地标签”的扩展。

**常规标签 vs 局部标签**
C 中常规标签有功能范围。其中作为本地标签的范围可以是内部嵌套块。因此，在一个函数中不能多次声明传统标签，而这正是使用本地标签的地方。

当标签在宏中并且宏在函数中被展开多次时，标签可以在函数中出现多次。例如，如果宏 funcMacro()的定义涉及块内的跳转指令(goto 语句)，并且 funcMacro 被函数 foo()多次使用。

```cpp
#define funcMacro(params …)
do {                                                    \
        if (cond == true)                               \
                goto x;                                 \
        <some code >                                    \
                                                        \
        x:                                              \
                <some code>                             \
} while(0);                                             \

Void foo()
{
    <some code>
    funcMacro(params …);
    <some code >
    funcMacro(params…);
}
```

在这样的函数 foo()中，函数宏将被扩展两次。
这会导致一个函数中有多个标签‘x’的定义，给编译器带来混乱，导致编译错误。在这种情况下，本地标签是有用的。

使用本地标签可以避免上述问题。本地标签声明如下:

```cpp
     __label__ label; 
```

本地标签声明必须出现在块的开头，在任何普通声明或语句之前。

下面是一个宏被多次展开的 C 例子。由于本地标签具有块范围，并且宏的每次扩展都会导致一个新的 do while 块，因此程序编译和运行良好。

```cpp
#include <stdio.h>
#include <string.h>

//Function macro using local labels
#define IS_STR_EMPTY(str)                                       \
do {                                                            \
        __label__  empty, not_empty, exit;                      \
        if (strlen(str))                                        \
                goto not_empty;                                 \
        else                                                    \
                goto empty;                                     \
                                                                \
        not_empty:                                              \
                printf("string  = %s\n", str);                  \
                goto exit;                                      \
        empty:                                                  \
                printf("string is empty\n");                    \
        exit: ;                                                 \
} while(0);                                                     \

int main()
{
        char string[20] = {'\0'};

        //Pass empty string to Macro function
        IS_STR_EMPTY(string);

        //Pass non-empty string to Macro function
        strcpy(string, "geeksForgeeks");
        IS_STR_EMPTY(string);

        return 0;
}                
```

输出:

```cpp
string is empty
string  = geeksForgeeks
```

本文由**喀什巴蒂亚**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论