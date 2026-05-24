# C 中浮动常数的大小()

> 原文:[https://www . geesforgeks . org/sizeof-floating-常量 in-c/](https://www.geeksforgeeks.org/sizeof-floating-constant-in-c/)

在 C 语言中，我们有三种浮动数据类型，即*浮动*、*双*和*长双*。这三种类型的确切大小取决于 C 编译器的实现/平台。下面的程序可以用来找出机器上每个浮动数据类型的大小。

```cpp
#include "stdio.h"
int main()
{
 printf("%d %d %d",sizeof(float), sizeof(double), sizeof(long double));
 return 0;
}
```

但是浮点常数的大小呢(例如 31.4 或 2.718)？例如，如果我们有如下定义的 PI 宏，那么(3.14)的大小是多少。

**#定义 PI 3.14**

现在如果我们做 *sizeof(PI)* ，它的大小会是多少？等于*大小的(浮动)*？或者它也依赖于编译器实现。好吧，对于浮动常数，C 标准(C11，即 ISO/IEC 9899:2011)给出了指导方针。根据 6.4.4.2 C11 条款，“*一个非固定的浮动常数有双精度类型。如果以字母 F 或 F 为后缀，则它具有类型 float。如果以字母 L 或 L 为后缀，则它具有长双精度类型。*”

表示浮动常数的类型与*双*数据类型相同。所以如果机器上的双*T4 的大小是 8 字节，那么浮点常数的大小就是 8 字节。你可以通过下面的程序*

```cpp
*#include "stdio.h"
#define PI 3.14
int main()
{
 printf("%d",sizeof(PI));
 return 0;
}*
```

*找到这个*

根据上面提到的 C 标准条款，一个浮动常数可以用 f 或 f 转换成 *float* 类型，同样，一个浮动常数可以用 l 或 l 转换成 *long double* ，所以猜测下面的输出应该不用多想:

```cpp
#include "stdio.h"
int main()
{
 printf("%d %d",sizeof(3.14F), sizeof(3.14L));
 return 0;
}
```

如果你觉得以上有用，请做 Like/Tweet/G+1。此外，请给我们留下进一步澄清或信息的评论。我们很乐意帮助和学习🙂