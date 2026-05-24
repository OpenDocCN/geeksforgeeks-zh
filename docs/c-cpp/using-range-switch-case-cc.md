# C/c++

中开关情况下的使用范围

> 原文:[https://www.geeksforgeeks.org/using-range-switch-case-cc/](https://www.geeksforgeeks.org/using-range-switch-case-cc/)

大家都很熟悉 C/C++ 中的[开关格](https://www.geeksforgeeks.org/switch-statement-cc/)，但是你知道**在 case 语句中可以用数字范围**代替单个数字或字符。

*   这是 GNU C 编译器的用例范围扩展，而不是标准的 C 或 C++
*   您可以在单个案例标签中指定连续值的范围，如下所示:

```cpp
case low ... high:
```

*   它可以用于 ASCII 字符代码的范围，如下所示:

```cpp
 case 'A' ... 'Z':
```

*   你需要在省略号 **…** 周围写空格。例如，写下以下内容:

```cpp
// Correct  -   case 1 ... 5:
// Wrong -    case 1...5: 
```

## C++

```cpp
// C++ program to illustrate
// using range in switch case
#include <iostream>
using namespace std;
int main()
{
    int arr[] = { 1, 5, 15, 20 };

    for (int i = 0; i < 4; i++)
    {
        switch (arr[i])
        {
        case 1 ... 6:
            cout << arr[i] <<" in range 1 to 6\n";
            break;
        case 19 ... 20:
            cout << arr[i] <<" in range 19 to 20\n";
            break;
        default:
            cout << arr[i] <<" not in range\n";
            break;
        }
    }
    return 0;
}

 //This code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to illustrate
// using range in switch case
#include <stdio.h>
int main()
{
    int arr[] = { 1, 5, 15, 20 };

    for (int i = 0; i < 4; i++)
    {
        switch (arr[i])
        {
        case 1 ... 6:
            printf("%d in range 1 to 6\n", arr[i]);
            break;
        case 19 ... 20:
            printf("%d in range 19 to 20\n", arr[i]);
            break;
        default:
            printf("%d not in range\n", arr[i]);
            break;
        }
    }
    return 0;
}
```

**输出:**

```cpp
1 in range 1 to 6
5 in range 1 to 6
15 not in range
20 in range 19 to 20
```

***时间复杂度:** O(n)，其中 n 是*数组 arr 的*大小。*

***辅助空间:**O(1)*
T5】练习:可以通过修改 char 数组和 case 语句来尝试上面的 char 数组程序。
**错误条件:**

1.  **低>高:**编译器给出错误信息。
2.  **重叠案例值:**如果案例标签的值在 switch 语句中已经使用过的案例范围内，编译器会给出错误消息。

本文由[曼德普·辛格](https://github.com/msdeep14)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。