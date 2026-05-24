# C 和 C++ 中的逗号

> 原文:[https://www.geeksforgeeks.org/comna-in-c-and-c/](https://www.geeksforgeeks.org/comna-in-c-and-c/)

在 C 和 C++ 中，逗号(，)可以在两种上下文中使用:
1)逗号作为运算符:
逗号运算符(由标记表示)是一个二进制运算符，它计算其第一个操作数并丢弃结果，然后计算第二个操作数并返回该值(和类型)。逗号运算符是所有 C 运算符中优先级最低的一个，充当[序列点](http://en.wikipedia.org/wiki/Sequence_point)。

## C

```cpp
/* comma as an operator */
int i = (5, 10); /* 10 is assigned to i*/
int j = (f1(), f2()); /* f1() is called (evaluated) first followed by f2().
                      The returned value of f2() is assigned to j */
```

2)逗号作为分隔符:
当与函数调用和定义、函数(如宏、变量声明、枚举声明和类似构造)一起使用时，逗号充当分隔符。

## C

```cpp
/* comma as a separator */
int a = 1, b = 2;
void fun(x, y);
```

逗号用作分隔符不应与运算符混淆。例如，在下面的语句中，f1()和 f2()可以以任何顺序调用。

## C

```cpp
/* Comma acts as a separator here and doesn't enforce any sequence.
    Therefore, either f1() or f2() can be called first */
void fun(f1(), f2());
```

C 与 C++ 使用逗号运算符的区别见[本](https://www.ibm.com/support/knowledgecenter/SSGH3R_16.1.0/com.ibm.xlcpp161.aix.doc/language_ref/co.html)。
你可以试试下面的程序来检查你对 C.
中逗号的理解

## C

```cpp
// PROGRAM 1
#include <stdio.h>
int main()
{
    int x = 10;
    int y = 15;

    printf("%d", (x, y));
    getchar();
    return 0;
}
```

## C

```cpp
// PROGRAM 2:  Thanks to Shekhu for suggesting this program
#include <stdio.h>
int main()
{
    int x = 10;
    int y = (x++, ++ x);
    printf("%d", y);
    getchar();
    return 0;
}
```

## C

```cpp
// PROGRAM 3:  Thanks to Venki for suggesting this program
#include <stdio.h>
int main()
{
    int x = 10, y;

    // The following is equivalent
    // to y = x + 2 and x += 3,
    // with two printings
    y = (x++,
         printf("x = %d\n", x),
         ++ x,
         printf("x = %d\n", x),
         x++);

    // Note that last expression is evaluated
    // but side effect is not updated to y
    printf("y = %d\n", y);
    printf("x = %d\n", x);

    return 0;
}
```

代码中的以下表达式:

a = 2，3，4；

评估为:

(((a = 2)，3)，4)；

这是因为赋值运算符的优先级高于逗号运算符。

## C++

```cpp
#include <iostream>

using namespace std;

int main()

{

    int a = 5;

    a = 2, 3, 4;

    cout << a;

    return 0;
}
```

3)逗号运算符代替分号。
我们知道在 C 和 C++ 中，每条语句都以分号结束，但逗号运算符也用于在满足以下规则后终止语句。

*   变量声明语句必须以分号结束。
*   声明语句之后的语句可以用逗号运算符终止。
*   程序的最后一条语句必须以分号结束。

**例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;
int main()
{
    cout << "First Line\n",
        cout << "Second Line\n",
        cout << "Third Line\n",
        cout << "Last line";
    return 0;
}
```

**输出:**

```cpp
First Line
Second Line
Third Line
Last line
```

尽量不要混淆逗号作为分隔符和逗号作为运算符。示例:

int a = 4，3；

这将生成一个错误，因为在这种情况下，逗号在声明发生时充当分隔符。因此无错误代码如下:

int a；

a = 4，3；

现在存储在 a 中的值将是 4。

同样，以下内容也是有效的，

int a =(4，3)；

这里，3 存储在。

参考文献:
[【http://en.wikipedia.org/wiki/Comma_operator】](http://en.wikipedia.org/wiki/Comma_operator)
[http://publib . boulder . IBM . com/info center/comp help/v 101v 121/index . JSP？topic =/com . IBM . xlcpp 101 . AIX . doc/language _ ref/co . html](http://publib.boulder.ibm.com/infocenter/comphelp/v101v121/index.jsp?topic=/com.ibm.xlcpp101.aix.doc/language_ref/co.html)
[http://msdn.microsoft.com/en-us/library/zs06xbxh.aspx](http://msdn.microsoft.com/en-us/library/zs06xbxh.aspx)
如发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息。