# C 中的整数促销

> 原文:[https://www.geeksforgeeks.org/integer-promotions-in-c/](https://www.geeksforgeeks.org/integer-promotions-in-c/)

像 *char* 、 *short int* 这样的数据类型比 *int* 占用的字节数少，当对它们执行操作时，这些数据类型会自动提升为 *int* 或*无符号 int* 。这叫整数推广。例如，像 *char* 、 *short* 和 *enum* 这样的较小类型不会发生算术计算。首先将其转换为 *int* 或*无符号 int* ，然后对其进行算术运算。如果 *int* 可以表示原始类型的所有值，则该值会转换为 *int* 。否则，将其转换为*无符号整数。*

例如，请参见以下程序。

```cpp
#include <stdio.h> 
int main()
{
    char a = 30, b = 40, c = 10;
    char d = (a * b) / c;
    printf ("%d ", d); 
    return 0;
}
```

输出:

```cpp
120
```

乍一看，表达式(a*b)/c 似乎会导致算术溢出，因为有符号字符只能有-128 到 127 之间的值(在大多数 C 编译器中)，子表达式'(a*b ')的值是 1200，大于 128。但是整数提升发生在对字符类型进行的算术运算中，我们得到了适当的结果，没有任何溢出。

把下面的程序看作**另一个例子**。

```cpp
#include <stdio.h>

int main()
{
    char a = 0xfb;
    unsigned char b = 0xfb;

    printf("a = %c", a);
    printf("\nb = %c", b);

    if (a == b)
      printf("\nSame");
    else
      printf("\nNot Same");
    return 0;
}
```

输出:

```cpp
a = ?
b = ?
Not Same 
```

当我们打印‘a’和‘b’时，打印的是相同的字符，但是当我们比较它们时，我们得到的输出是“不相同”。
“a”和“b”具有与*字符*相同的二进制表示。但是当对“a”和“b”执行比较操作时，它们首先被转换为 int。“a”是一个带符号的*字符*，当它被转换为 *int* 时，它的值变成-5(带符号的值 0xfb)。b’是*无符号字符*，当它被转换成 *int* 时，它的值变成 251。值-5 和 251 有不同的表示为 *int* ，所以我们得到的输出为“不相同”。

我们很快将讨论有符号和无符号、int 和 long int 等之间的整数转换规则。

**参考文献:**
[http://www . tru 64 UNIX . Compaq . com/docs/base _ doc/DOCUMENTATION/V40F _ HTML/AQTLTBTE/DOCU _ 067。HTM](http://www.tru64unix.compaq.com/docs/base_doc/DOCUMENTATION/V40F_HTML/AQTLTBTE/DOCU_067.HTM)

本文由**阿沛·拉提**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论