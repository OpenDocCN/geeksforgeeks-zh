# 奎因——一个自我复制程序

> 原文:[https://www . geesforgeks . org/Quine-a-自我复制-程序/](https://www.geeksforgeeks.org/quine-a-self-reproducing-program/)

quine 是一个程序，它打印自己的副本作为唯一的输出。奎因不需要输入。奎因是以美国数学家和逻辑学家威拉德·范·奥曼·奎因(1908-2000)的名字命名的。有趣的是你不允许使用打开然后打印文件的程序。

据我们所知，下面是 c 中最短的蒯因。

```cpp
main() { char *s="main() { char *s=%c%s%c; printf(s,34,s,34); }"; printf(s,34,s,34); } 
```

该程序使用 printf 函数，但不包含其对应的头文件(#include <stdio.h>)，这可能导致未定义的行为。此外，main 的返回类型声明被省略，以减少程序的长度。两个 34 用于在字符串 s 周围打印双引号</stdio.h>

以下是由*纳伦德拉*建议的上述程序的较短版本。

```cpp
main(a){printf(a="main(a){printf(a=%c%s%c,34,a,34);}",34,a,34);}
```

如果你找到了更短的 C 蒯因或者你想用其他编程语言分享蒯因，那么请在评论区做写。

[蟒中奎因](https://www.geeksforgeeks.org/quine-in-python/)

来源:
[http://en.wikipedia.org/wiki/Quine_%28computing%29](http://en.wikipedia.org/wiki/Quine_%28computing%29)