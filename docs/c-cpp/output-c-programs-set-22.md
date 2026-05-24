# c++ 程序输出|第 22 集

> 原文:[https://www.geeksforgeeks.org/output-c-programs-set-22/](https://www.geeksforgeeks.org/output-c-programs-set-22/)

预测以下 C++ 程序的输出。

**问题 1**

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a = b = c = 0;
    cout << a << "*" << b << "*" << c;
    return 0;
}
```

输出:

```cpp
Compile time error!

```

**说明:**
声明时不能用链式语句初始化变量。因此陈述 a = b = c = 0；是非法的陈述。但是遵循合法的语法，可以用在 C++ 或 C 中

```cpp
int a,b,c;
      a = b = c = 0;

```

**问题 2**

```cpp
#include <iostream>
using namespace std;

int main()
{
    for ( ; ; ) cout << "blank";
    return 0;
}
```

输出:

```cpp
Infinite Loop!

```

**说明:**
由于循环内部缺少初始化、测试条件和递增/递减条件，执行将陷入无限循环。

**问题 3**

```cpp
#include <iostream>
using namespace std;

int main()
{  
   int i;
   for (i=0; i<3; i++);

   cout << "hello!" <<i;

   return 0;

}
```

输出:

```cpp
hello!3

```

**解说:**
你好！3 是结果，因为当 for 循环执行时，由于分号(；)出现在已定义 for 循环的行中。循环将执行三次，I 的值将变为 3，然后语句的其余部分将执行。

**问题 4**

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i;
    i = 1 + (1,4,5,6,3);
    cout << i;
    return 0;
}
```

输出:

```cpp
4

```

**解释:**
逗号(，)运算符是一个二元运算符，它计算第一个操作数并丢弃结果，然后计算第二个操作数并返回第二个操作数的值。这里逗号(，)运算符的关联性是从左到右的，很容易理解表达式(1，4，5，6，3)的计算结果是 3，然后将结果 1 + 3 赋给 I。

**问题 5**

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a = 0, b;
    b = (a = 50) + 10;
    cout << a << "{content}quot; << b;
    return 0;
}
```

输出:

```cpp
50$60

```

**解释:**
语句 b =(a = 50)+10；使用嵌入赋值的概念。这里，值 50 分配给变量 a，结果 50+10 分配给 b。

**问题 6**

```cpp
#include<iostream>
using namespace std;

int main()
{
    char a = 30, b = 40, c = 10;
    char d = (a*b)/c;
    cout << int(d);

    return 0;
}
```

输出:

```cpp
120

```

**说明:**
如果对字符数据类型的变量进行算术运算，C++ 也可以考虑字符的 ASCII 值进行算术计算。在这种情况下，答案是 120，这是 x 的 ASCII 值。

**问题 7**

```cpp
#include<iostream>
using namespace std;

int main(int x)
{
    static int i = 5;

    if (--i)
    {
        cout << i;
        main(10);
    }
    return 0;
}
```

输出:

```cpp
4321

```

**说明:**
c++ 中的任何非零数字都被视为真值。在这段代码中，if 语句倾向于减少 I 的值，但是在 if 块中，main()函数被一次又一次地调用。在这里，程序似乎处于无限循环中，但是变量 I 本质上是静态的，它有它的生命周期，直到执行，因此，如果我变成 0，程序将停止。

**问题 8**

```cpp
#include<iostream>
using namespace std;

int main(int x)
{
    int i = 5;

    if (--i)
    {
        cout << i;
        main(10);
    }
    return 0;
}
```

输出:

```cpp
infinite loop

```

**说明:**
c++ 中的任何非零数字都被视为真值。在这段代码中，if 语句倾向于减少 I 的值，但是在 if 块中，main()函数被一次又一次地调用(所有语句现在都将像新程序一样执行)，因此程序执行将陷入无限循环，因为没有终止条件。

本文由**阿维纳什库马尔辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。