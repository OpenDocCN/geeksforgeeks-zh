# typedef 与 C 中定义的#对比

> 原文:[https://www.geeksforgeeks.org/typedef-versus-define-c/](https://www.geeksforgeeks.org/typedef-versus-define-c/)

**typedef**:typedef 用来给数据类型一个新的名字。例如

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

C 语言中的 **#define** 是一个指令，用来#定义别名。

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

**typedef 和#define 的区别:**

1.  Typedef is limited to assigning symbolic names to types, and #define can also be used to define aliases of values. For example, you can define 1 as ONE and 3.14 as PI.
2.  Typedef interpretation is executed by the compiler, where the #define statement is executed by the preprocessor.
3.  #define should not end with a semicolon, but typedef should end with a semicolon.
4.  #define will only copy and paste the definition value at the point of use, while typedef is the actual definition of the new type.
5.  Typedef follows the scope rule, which means that if a new type is defined in a scope (inside a function), the new type name is only visible when the scope exists. In the case of #define, when the preprocessor encounters #define, it will replace all subsequent events (without following the scope rule).

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

从上述程序的输出来看，指针“a”的大小是 8(在使用 8 字节存储指针的机器上)。在上面的程序中，当编译器来到

```cpp
typedef char* ptr;
ptr a, b, c;
```

时

该声明实际上成为

```cpp
char *a, *b, *c;
```

这将 a、b、c 声明为 char*。

相比之下，#像这样定义作品:

```cpp
#define PTR char*
PTR x, y, z;

```

该声明实际上成为

```cpp
char *x, y, z;
```

这使得 x、y 和 z 不同，因为，x 是指向字符的指针，而 y 和 z 是字符变量。当我们在定义时用指针声明宏时，如果我们声明了多个标识符，那么实际的定义是给第一个标识符的，其余的是非指针定义。在上面的例子中，x 将被声明为 char*，所以它的大小是指针的大小，而 y 和 z 将被声明为 char，所以它们的大小是 1 字节。

本文由 **HARISH KUMAR** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。