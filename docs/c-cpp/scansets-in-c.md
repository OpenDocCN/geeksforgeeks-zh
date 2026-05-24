# C 中的扫描组

> 原文:[https://www.geeksforgeeks.org/scansets-in-c/](https://www.geeksforgeeks.org/scansets-in-c/)

scanf 系列函数支持由%[]表示的 scanset 说明符。在 scanset 中，我们可以指定单个字符或字符范围。在处理扫描集时，scanf 将只处理扫描集中的那些字符。我们可以通过将字符放在方括号内来定义 scanset。请注意，扫描集区分大小写。

我们还可以通过在您想要添加的字符之间提供逗号来使用 scanset。

示例:scanf(%s[A-Z，_，A，b，c]s，str)；

这将扫描扫描集中的所有指定字符。
让我们用例子来看看。以下示例将只存储大写字母到字符数组' str '，任何其他字符都不会存储在字符数组中。

## C

```cpp
/* A simple scanset example */
#include <stdio.h>

int main(void)
{
    char str[128];

    printf("Enter a string: ");
    scanf("%[A-Z]s", str);

    printf("You entered: %s\n", str);

    return 0;
}
```

```cpp
  [root@centos-6 C]# ./scan-set 
  Enter a string: GEEKs_for_geeks
  You entered: GEEK
```

如果扫描集的第一个字符是'^'，则说明符将在第一次出现该字符后停止读取。例如，下面给出的 scanset 将读取所有字符，但在第一次出现“o”后停止

## C

```cpp
scanf("%[^o]s", str);
```

让我们举个例子来看看。

## C

```cpp
/* Another scanset example with ^ */
#include <stdio.h>

int main(void)
{
    char str[128];

    printf("Enter a string: ");
    scanf("%[^o]s", str);

    printf("You entered: %s\n", str);

    return 0;
}
```

```cpp
  [root@centos-6 C]# ./scan-set 
  Enter a string: http://geeks for geeks
  You entered: http://geeks f
  [root@centos-6 C]# 
```

让我们通过使用扫描集来实现 get()函数。get()函数将一行从 stdin 读入 s 指向的缓冲区，直到找到终止换行符或 EOF。

## C

```cpp
/* implementation of gets() function using scanset */
#include <stdio.h>

int main(void)
{
    char str[128];

    printf("Enter a string with spaces: ");
    scanf("%[^\n]s", str);

    printf("You entered: %s\n", str);

    return 0;
}
```

```cpp
  [root@centos-6 C]# ./gets 
  Enter a string with spaces: Geeks For Geeks
  You entered: Geeks For Geeks
  [root@centos-6 C]# 
```

顺便提一下，使用 get()通常不是一个好主意。从 Linux 手册页查看下面的注释。
*千万不要用 get()。因为如果不事先知道数据，就不可能知道 get()将读取多少个字符，而且因为 get()将继续存储超过缓冲区末尾的字符，所以使用起来极其危险。它已经被用来破坏计算机安全。请改用 fgets()。*另见[本](https://www.geeksforgeeks.org/gets-is-risky-to-use/)帖。
本文由“纳伦德拉·康拉尔卡尔”编辑，GeeksforGeeks 团队审核。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。