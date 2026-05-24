# strxfrm()

## C/C++

> 原文: [https://www.geeksforgeeks.org/strxfrm-in-ccpp/](https://www.geeksforgeeks.org/strxfrm-in-ccpp/)

C/C++ 库函数 `strxfrm()` 将源字符串的字符转换为当前区域设置，并将其放置在目标字符串中。
转换使用在 `<locale.h>` 中定义的 `LC_COLLATE` 类别。`strxfrm()` 函数执行转换的方式是，对两个转换后的字符串使用 `strcmp()` 的结果，与对两个原始字符串使用 `strcoll()` 的结果相同。

### 语法:

```cpp
size_t strxfrm(char *str1, const char *str2, size_t num);
```

参数:
- `str1`：指向接收转换后字符串前 `num` 个字符的目标数组的指针。
- `str2`：指向要转换的源字符串的指针。
- `num`：要复制到 `str1` 中的最大字符数。

### 示例:

**示例 1：**

输入：`'geeksforgeeks'`
输出：`13`

```cpp
// C program to demonstrate strxfrm()
#include <stdio.h>
#include <string.h>
int main()
{
    char src[10], dest[10];
    int len;
    strcpy(src, "geeksforgeeks");
    len = strxfrm(dest, src, 10);
    printf("Length of string %s is: %d", dest, len);
    return (0);
}
```

输出：

```
Length of string geeksforgeeks is: 13
```

**示例 2：**

输入：`'hello geeksforgeeks'`
输出：`20` // 在此示例中，空格也被计算在内

```cpp
// C program to demonstrate strxfrm()
#include <stdio.h>
#include <string.h>
int main()
{
    char src[20], dest[200];
    int len;
    strcpy(src, " hello geeksforgeeks");
    len = strxfrm(dest, src, 20);
    printf("Length of string %s is: %d", dest, len);
    return (0);
}
```

输出：

```
Length of string  hello geeksforgeeks is: 20
```

**示例 3：**

```cpp
// C program to demonstrate strxfrm()
#include <iostream>
#include <string.h>
using namespace std;
int main()
{
    char str2[30] = "Hello geeksforgeeks";
    char str1[30];
    cout << strxfrm(str1, str2, 4) << endl;
    cout << str1 << endl;
    cout << str2 << endl;
    return 0;
}
```

输出：

```
Hell
Hello geeksforgeeks
```

本文由**希瓦尼·巴盖尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。