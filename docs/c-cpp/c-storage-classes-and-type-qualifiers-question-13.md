# C |存储类和类型限定符|问题 19

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-13/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-13/)

输出？(GATE CS 2012)

```cpp
#include <stdio.h>
int a, b, c = 0;
void prtFun (void);
int main ()
{
    static int a = 1; /* line 1 */
    prtFun();
    a += 1;
    prtFun();
    printf ( "\n %d %d " , a, b) ;
}

void prtFun (void)
{
    static int a = 2; /* line 2 */
    int b = 1;
    a += ++ b;
    printf (" \n %d %d " , a, b);
}
```

**(A)**3 1
4 1
4 2
T5】(B)4 2
6 1
6 1
T10】(C)4 2
6 2
2 0
T15】(D)3 1
5 2
5 2

**回答:** **(C)**

**说明:**‘a’和‘b’是全局变量。prtFun()也有“a”和“b”作为局部变量。局部变量隐藏全局变量(参见 C 中的[作用域规则)。第一次调用 prtFun()时，本地“b”变为 2，本地“a”变为 4。
第二次调用 prtFun()时，使用本地静态“a”的相同实例，并创建“b”的新实例，因为“a”是静态的，“b”是非静态的。所以 b 又变成了 2，a 变成了 6。
main()也有自己的名为‘a’的局部静态变量，它隐藏了 main 中的全局‘a’。main()中的 printf()语句访问本地“a”并打印其值。同一 printf()语句访问全局“b”，因为 main 中没有名为“b”的局部变量。此外，静态和全局 int 变量的默认值为 0。这就是为什么 main()中的 printf 语句将 0 打印为 b 的值。](https://www.geeksforgeeks.org/archives/15415) [本题的测验](https://www.geeksforgeeks.org/c-language-2-gq/storage-classes-gq/)