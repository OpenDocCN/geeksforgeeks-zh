# C 编程中的有趣事实

> 原文:[https://www . geesforgeks . org/interior-facts-in-c-programming/](https://www.geeksforgeeks.org/interesting-facts-in-c-programming/)

下面是一些关于 C 编程的有趣事实:

**1)**switch 语句的事例标签可以出现在 if-else 语句内部。

```cpp
#include <stdio.h>

int main()
{
    int a = 2, b = 2;
    switch(a)
    {
    case 1:
        ;

        if (b==5)
        {
        case 2:
            printf("GeeksforGeeks");
        }
    else case 3:
    {

    }
    }
}
```

输出:

```cpp
GeeksforGeeks
```

**2)** arr[index]与 index[arr]
相同，其工作原理是，使用指针算法访问数组元素。

```cpp
// C program to demonstrate that arr[0] and
// 0[arr]
#include<stdio.h>
int main() 
{
    int arr[10];
    arr[0] = 1;
    printf("%d", 0[arr] );

    return 0;    
}
```

输出:

```cpp
1
```

**3)** 我们可以用“<:，:>”代替“[，]”和“< %，% >”代替“{，}”

```cpp
#include<stdio.h>
int main()
<%
    int arr <:10:>;
    arr<:0:> = 1;
    printf("%d", arr<:0:>);

    return 0;
%>
```

输出:

```cpp
1
```

**4)** 在陌生地方使用#include。
让“a.txt”包含(“geeks forgeeks”)；

```cpp
#include<stdio.h>
int main()
{
    printf
    #include "a.txt"
    ;
}
```

输出:

```cpp
GeeksforGeeks
```

**5)** 我们可以通过在格式说明符“%”后使用“*”来忽略 scanf()中的输入

```cpp
#include<stdio.h>
int main()
{
    int a;

    // Let we input 10 20, we get output as 20
    // (First input is ignored)
    // If we remove * from below line, we get 10.
    scanf("%*d%d", &a);

    printf( "%d ",  a);  

    return 0;     
}
```

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。