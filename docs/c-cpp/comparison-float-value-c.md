# 浮点数与 C 中值的比较

> 原文:[https://www.geeksforgeeks.org/comparison-float-value-c/](https://www.geeksforgeeks.org/comparison-float-value-c/)

预测以下 C 程序的输出。

## C

```cpp
#include<stdio.h>
int main()
{
    float x = 0.1;
    if (x == 0.1)
        printf("IF");
    else if (x == 0.1f)
        printf("ELSE IF");
    else
        printf("ELSE");
}
```

上述程序的输出为“***【ELSE IF】***”，表示表达式“x == 0.1”返回假，表达式“x == 0.1f”返回真。

让我们考虑以下程序来理解上述输出背后的原因。

## C

```cpp
#include<stdio.h>
int main()
{
   float x = 0.1;
   printf("%d %d %d", sizeof(x), sizeof(0.1), sizeof(0.1f));
   return 0;
}
```

```cpp
The output of above program is "***4 8 4***" on a typical C compiler.
It actually prints size of float, size of double and size of float.

```

表达式中使用的值被视为双精度([双精度浮点格式](http://en.wikipedia.org/wiki/Double_precision_floating-point_format))，除非在末尾指定了“f”。所以表达式“x==0.1”在右侧有一个双精度浮点数，在左侧以[单精度浮点格式](http://en.wikipedia.org/wiki/Single_precision_floating-point_format)存储。在这种情况下，float 被提升为双倍(参见[本](http://publib.boulder.ibm.com/infocenter/comphelp/v101v121/index.jsp?topic=/com.ibm.xlcpp101.aix.doc/language_ref/cplr066.html))。双精度格式比单精度格式使用更多的精度位。

0.1 <sub>10</sub> 的二进制等价可以写成(0.00011001100110011……)<sub>2</sub>向上无穷大(更多关于换算的知识，请参见[这篇](https://www.geeksforgeeks.org/convert-decimal-fraction-binary-number/)文章)。由于浮点的精度小于两倍，因此在某个点(浮点为 23，双倍为 52)之后，它会截断结果。因此，在将浮点提升为双精度(在比较时)后，编译器会用零填充剩余的位。因此，我们得到了不同的结果，其中两者的十进制等价是不同的。例如，

```cpp
In float 
=> (0.1)10 = (0.00011001100110011001100)2
In double after promotion of float ...(1)
=> (0.1)10 = (0.00011001100110011001100000000000000000...)2
                                      ^ padding zeroes here
In double without promotion ... (2)
=> (0.1)10 = (0.0001100110011001100110011001100110011001100110011001)2

Hence we can see the result of both equations are different.
Therefore 'if' statement can never be executed.

```

请注意，将浮点提升为双精度只会在值(如 0.1)比单精度位使用更多精度位时导致不匹配。例如，下面的 C 程序打印“IF”。

## C

```cpp
#include<stdio.h>
int main()
{
    float x = 0.5;
    if (x == 0.5)
        printf("IF");
    else if (x == 0.5f)
        printf("ELSE IF");
    else
        printf("ELSE");
}
```

**输出:**

```cpp
IF

```

这里二进制等价的 0.5 <sub>10</sub> 是(0.100000…) <sub>2</sub>

(浮点型和双精度型都不会丢失精度)。因此，如果编译器在升级时填充额外的零，那么在比较中，我们将在左侧和右侧的十进制等价物中获得相同的结果(x == 0.5)。

浮点数的表示可以参考[浮点数表示–基础](https://www.geeksforgeeks.org/floating-point-representation-basics/)。

本文由 **Abhay Rathi** 供稿， **SHUBHAM BANSAL** 改进。如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的话题的信息