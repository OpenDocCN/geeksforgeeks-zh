# typedef 与 #define 在 C 中的对比

> 原文: [https://www.geeksforgeeks.org/typedef-versus-define-c/](https://www.geeksforgeeks.org/typedef-versus-define-c/)

## typedef

`typedef` 用来给数据类型一个新的名字。例如：

```cpp
// C program to demonstrate typedef
#include <stdio.h>

// After this line BYTE can be used
// in place of unsigned char
typedef unsigned char BYTE;

int main()
{
    BYTE b1, b2;
    b1 = 'c';
    printf("%c ", b1);
    return 0;
}
```

**输出:**

```cpp
c
```

## #define

C 语言中的 `#define` 是一个指令，用来定义别名。

```cpp
// C program to demonstrate #define
#include <stdio.h>

// After this line HYD is replaced by
// "Hyderabad"
#define HYD "Hyderabad"

int main()
{
    printf("%s ", HYD);
    return 0;
}
```

**输出:**

```cpp
Hyderabad
```

## typedef 和 #define 的区别

1.  `typedef` 仅限于为类型分配符号名称，而 `#define` 也可用于定义值的别名。例如，你可以将 1 定义为 `ONE`，将 3.14 定义为 `PI`。
2.  `typedef` 解释由编译器执行，而 `#define` 语句由预处理器执行。
3.  `#define` 不应以分号结尾，但 `typedef` 应以分号结尾。
4.  `#define` 只会在使用点复制并粘贴定义值，而 `typedef` 是新类型的实际定义。
5.  `typedef` 遵循作用域规则，这意味着如果在某个作用域内（函数内部）定义了新类型，则该新类型名仅在该作用域存在时可见。对于 `#define`，当预处理器遇到 `#define` 时，它会替换所有后续出现（不遵循作用域规则）。

## 示例：typedef 相对于 #define 对数据类型的重要性

```cpp
// C program to demonstrate importance
// of typedef over #define for data types
#include <stdio.h>
typedef char* ptr;
#define PTR char*
int main()
{
    ptr a, b, c;
    PTR x, y, z;
    printf("sizeof a:%zu\n" ,sizeof(a) );
    printf("sizeof b:%zu\n" ,sizeof(b) );
    printf("sizeof c:%zu\n" ,sizeof(c) );
    printf("sizeof x:%zu\n" ,sizeof(x) );
    printf("sizeof y:%zu\n" ,sizeof(y) );
    printf("sizeof z:%zu\n" ,sizeof(z) );
    return 0;
}
```

**输出:**

```cpp
sizeof a:8
sizeof b:8
sizeof c:8
sizeof x:8
sizeof y:1
sizeof z:1
```

从上述程序的输出来看，指针 `a` 的大小是 8（在使用 8 字节存储指针的机器上）。在上面的程序中，当编译器遇到

```cpp
typedef char* ptr;
ptr a, b, c;
```

时，该声明实际上成为

```cpp
char *a, *b, *c;
```

这将 `a`、`b`、`c` 声明为 `char*`。

相比之下，`#define` 像这样工作：

```cpp
#define PTR char*
PTR x, y, z;
```

该声明实际上成为

```cpp
char *x, y, z;
```

这使得 `x`、`y` 和 `z` 不同，因为 `x` 是指向字符的指针，而 `y` 和 `z` 是字符变量。当我们在定义时用指针声明宏时，如果我们声明了多个标识符，那么实际的定义是给第一个标识符的，其余的是非指针定义。在上面的例子中，`x` 将被声明为 `char*`，所以它的大小是指针的大小，而 `y` 和 `z` 将被声明为 `char`，所以它们的大小是 1 字节。

本文由 **HARISH KUMAR** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。