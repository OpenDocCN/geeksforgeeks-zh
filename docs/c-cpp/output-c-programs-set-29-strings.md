# c++ 程序输出|第 29 集(字符串)

> 原文:[https://www . geesforgeks . org/output-c-programs-set-29-strings/](https://www.geeksforgeeks.org/output-c-programs-set-29-strings/)

先决条件:[字符串](https://www.geeksforgeeks.org/c-string-class-and-its-applications/)

*   **问题**
    **什么是输出？**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main()
{
    char s1[] = "geeksforgeeksforgeeks";
    char s2 = 'f';
    char *ptr = strchr( s1, s2);
    cout << ptr;
    return 0;
}
```

**输出:**

```cpp
forgeeksforgeeks
```

*   **描述:** strchr( str，c)返回一个指向字符串中第一个出现的字符‘c’的指针。这里 s2 是“f”，strchr()返回它在 s1 中第一次出现的地址。

*   **问题**
    **什么是输出？**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main()
{
    char s1[] = "geeksforgeeksforgeeks";
    char s2[] = "for";
    char *ptr = strstr(s1, s2);
    cout << ptr;
    return 0;
}
```

**输出:**

```cpp
forgeeksforgeeks
```

*   **描述:**strtr(str1，str2)返回一个指向 str 1 中第一个出现的字符串 str2 的指针。这里 s2 是“for”，strstr()返回它在 s1 中第一次出现的地址。

*   **问题**
    **什么是输出？**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

int main()
{
    char str[] = "geeksforgeeks";
    cout << 6[str];
    return 0;
}
```

**输出:**

```cpp
o
```

*   **说明:**对于编译器 6[str]与 str[6]相同。因此，它将搜索字符串“str”中的第 6 个元素，并打印它，在这种情况下是“o”。

*   **问题**
    **什么是输出？**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main ()
{
  char string[50] = "geeks, for:geeks";
  char *p;
  p = strtok (string, ", :" ); //, and ; are delimiteres.
  while (p != NULL)
  {
    cout << p << endl;
    p = strtok (NULL, ", :");
  }
  return 0;
}
```

**输出:**

```cpp
geeks
for
geeks
```

*   **描述:** strtok()用于使用分隔符对字符串进行标记或短语化。strtok()返回分隔符之前的字符串，并在字符串中的标记之后立即写入空值。

*   **问题**
    **什么是输出？**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main ()
{
  char string[50] = "geeksforgeeks";
  memset (string, '*', 8);
  cout << string;
  return 0;
}
```

**输出:**

```cpp
********geeks
```

*   **描述:**记忆集(字符串，c，n)将*字符串*的前 n 个字符设置为‘c’。在本程序中，*字符串*中的第一个“8”字符将被设置为“*”。我们经常在支票上看到这种文本，我们想在那里隐藏一些数据。关于记忆集的更多细节，请参考这里的

本文由 [I.HARISH KUMAR](https://www.facebook.com/harishkumar.injamuri) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。