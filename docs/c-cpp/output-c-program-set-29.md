# C 程序输出|第 29 集

> 原文:[https://www.geeksforgeeks.org/output-c-program-set-29/](https://www.geeksforgeeks.org/output-c-program-set-29/)

**问题 1**
main()会被叫多少次？

## C

```cpp
main()
{
   printf("\n main Called Again");
   main();
}
```

**回答:**无限循环
**描述:**main()中没有条件停止 main()的递归调用，因此称为无限次数。

**问题 2**
猜测以下程序的输出:

## C

```cpp
#include<stdio.h>
int main()
{
  int x = 10;
  float y = 10.0;
  if (x == y)
    printf("x and y are equal");
  else
    printf("x and y are not equal");
}
```

**回答:** x 和 y 相等
T3】描述:如果(x == y)这里我们比较的是 if (10 == 10.0)，因此这个条件成立。因为我们不能比较 int
和 float，所以 int 转换为 float，然后进行比较。因此它打印出“x 和 y 相等”。

**问题 3**
下面的代码会输出什么？

## C

```cpp
#include<string.h>
main()
{
    char *str1 = "abcd";
    char str2[] = "abcd";
    printf("%d %d %d", sizeof(str1),
          sizeof(str2), sizeof("abcd"));
}
```

**回答:**8 5 5
T3】描述:T5】在运行该程序的机器上打印第一个大小为 8 的字符指针。然后打印大小为 5 的字符串 str2 的大小(包括“/0”终止字符)。第三个和第二个相似。

**问题 4**
下面的 c 程序会输出什么？

## C

```cpp
#include "stdio.h"
int main()
{
    int _ = 18;
    int __ = 38;
    int ___;
    ___ = _ + __;
    printf ("%i", ___);
    return 0;
}
```

**回答:**56
T3】说明:变量名只能有**下划线。**

**问题 5**
下面操作的结果会是什么:

## C

```cpp
main()
{
    int x = 41, y = 43;
    x = y++ + x++ ;
    y = ++ y + ++ x;
    printf ("%d %d", x , y);
}
```

**答:**86 130
T3】说明:其实编译器相依。在 x = y++ + x++ 之后，x 的值变成 85，y 变成 44，y = +++ y+++ x 将被计算为 y = (44) + (86)。计算后 y 变成 130。

**问题 6**
下面操作的结果会是什么:

## C

```cpp
main()
{
    int x = 7;
    printf ("%d, %d, %d", x,
                 x<<5, x>>5);
}
```

**答案:** 7，224，0
**描述:**由于 x = 7 所以第一个%d 给出 7，第二个%d 左移 5 次后取 x 的值，将值转换为二进制后进行移位，二进制值 7 (000111)将左移两次使其为二进制 224(11100000)，所以 x < < 5 为 224，由于左移不会影响 x 的原始值，所以其仍为 5 的三分之一

**问题 7**
会输出什么？

## C

```cpp
main()
{
  if (1, 0)
    printf ("True");
  else
    printf ("False");
}
```

**答案:**假
**描述:**逗号(，)运算符返回**、**右侧的值，因此 if 语句变为 if(0)。

**问题 8**
输出是什么？

## C

```cpp
#include<stdio.h>
int main()
{
  printf ("%d", printf("%d", 12345678));
  return 0;
}
```

**回答:** 123456788
**说明:**注意末尾多了 8 个。printf()返回屏幕上成功打印的字符数。

**问题 9**
输出是什么？

## C

```cpp
void main()
{
  printf ("2 + 3 = %d", 2+3);
}
```

**回答:** 2 + 3 = 5
**说明:**由于格式说明符为%d，且两者均为整数(2，3)，因此会相加并打印整数值。

**问题 10**
输出是什么？

## C

```cpp
#include<stdio.h>
main()
{
    int i = 0;
    if (i = 55, 0, 10, 0)
        printf ("Test Skills %d", i);
    else
        printf ("C Programming %d", i);
}
```

**回答:** C 编程 55
T3】说明: i=55 先求值，其值丢弃。0 被评估，然后被丢弃。10 评估后丢弃。然后计算最右边的 0，它将是 if 条件中整个表达式的值(但不是子表达式的值)，并使条件为 false。

**问题 11**
输出是什么？

## C

```cpp
#include<stdio.h>
int main()
{
    char arr[5] = "World is beautiful";
    printf ("%s", arr);
    return 0;
}
```

**回答:**世界
还会打印一条警告“4:19:警告:字符数组的初始值设定项字符串太长[默认启用]”
T4】描述:任何字符数组的大小都不能小于它所分配的任何字符串中的字符数。数组的大小可以等于(不包括空字符)或大于，但不能小于。

**问题 12**
下面的程序输出是什么？

## C

```cpp
#include<stdio.h>
void main()
{
    int a = 2;
    switch (a)
    {
        case 4: printf ("A");
        break;
        case 3: printf ("B");
        default : printf("C");
        case 1 : printf ("D");
        break;
        case 5 : printf ("E");
    }
}
```

**回答:**CD
T3】说明:在 switch 语句中默认应该是 at 之后提到的所有 switch 情况。在这种情况下，它在中间执行，并且在 break 语句之前执行 default 之后的所有情况。

**问题 13**
输出是什么？

## C

```cpp
#include<stdio.h>
int main()
{
    int x = 100, y = 200;
    if ( ++ x || ++ y)
        printf ("x = %d, y = %d", x, y);
    else
        printf ("condition failed");
    return 0;
}
```

**回答:** x = 101，y = 200
**说明:**在 if 条件第一部分(即。，+++ x)首先执行，这里 x 值变成 101。

**问题 14**
考虑以下程序:

## C

```cpp
#include<stdio.h>
main()
{
    int i, j;
    for( i = 0, j = 5; j>0, i<10 ; i++, j--)
    printf ("\GeeksforGeeks.org");
}
```

“GeeksforGeeks.org”会被打印多少次？
**答案:** 10
**描述:**for 循环的条件部分(j > 0，i < 10)用逗号分隔，这意味着编译器将使用逗号右侧的值，即 i < 10 的值，因此循环将执行
直到 I 的值小于 10。

**问题 15**
输出是什么？

## C

```cpp
#include<stdio.h>
#define SQR( x ) ( x * x )
int main()
{
    int b = 5;
    int a = SQR(b+2);
    printf("%d\n", a);
    return 0;
}
```

**回答:** 17
**描述:**我们知道宏会盲目代入，不算。它将首先替换该值，然后再进行计算。因此，在替换之后，宏将变成 SQR( x + 2) = ( x + 2 * x + 2)，在这种情况下，x 值为 5。所以，最后的换人将是 SQR(5 + 2 ) = (5 + 2 * 5 + 2)。因为“*”比“+”具有更高的优先级，所以它将变成(5 + 10 + 2)。在这种情况下，a 的值将是 17

本文由**哈里什·库马尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。