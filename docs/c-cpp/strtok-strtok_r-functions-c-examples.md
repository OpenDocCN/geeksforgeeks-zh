# strtok()和 strtok_r()函数在 C 语言中有示例

> 原文:[https://www . geesforgeks . org/strtok-strtok _ r-functions-c-examples/](https://www.geeksforgeeks.org/strtok-strtok_r-functions-c-examples/)

c 提供了两个函数 strtok()和 strtok_r()，用于通过某种分隔符拆分字符串。拆分字符串是一项非常常见的任务。例如，我们有一个逗号分隔的文件项目列表，我们想要一个数组中的单个项目。
**strtok()**

```cpp
// Splits str[] according to given delimiters.
// and returns next token. It needs to be called
// in a loop to get all tokens. It returns NULL
// when there are no more tokens.
char * strtok(char str[], const char *delims);
```

## C

```cpp
// A C/C++ program for splitting a string
// using strtok()
#include <stdio.h>
#include <string.h>

int main()
{
    char str[] = "Geeks-for-Geeks";

    // Returns first token
    char* token = strtok(str, "-");

    // Keep printing tokens while one of the
    // delimiters present in str[].
    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, "-");
    }

    return 0;
}
```

输出:

```cpp
Geeks
for
Geeks
```

**strtok_r()**
就像 C 语言中的 strtok()函数一样，strtok_r()也执行同样的任务，将一个字符串解析成一个令牌序列。strtok_r()是 strtok()
的[重入](https://www.geeksforgeeks.org/reentrant-function/)版本，我们有两种方法可以调用 strtok_r()

```cpp
// The third argument saveptr is a pointer to a char * 
// variable that is used internally by strtok_r() in 
// order to maintain context between successive calls
// that parse the same string.
char *strtok_r(char *str, const char *delim, char **saveptr);
```

下面是一个简单的 C 程序，展示了 strtok_r()的用法:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C program to demonstrate working of strtok_r()
// by splitting string based on space character.
#include <stdio.h>
#include <string.h>

int main()
{
    char str[] = "Geeks for Geeks";
    char* token;
    char* rest = str;

    while ((token = strtok_r(rest, " ", &rest)))
        printf("%s\n", token);

    return (0);
}
```

输出:

```cpp
Geeks
for
Geeks
```

**strtok 的另一个例子:**

## C

```cpp
// C code to demonstrate working of
// strtok
#include <stdio.h>
#include <string.h>

// Driver function
int main()
{
    // Declaration of string
    char gfg[100] = " Geeks - for - geeks - Contribute";

    // Declaration of delimiter
    const char s[4] = "-";
    char* tok;

    // Use of strtok
    // get first token
    tok = strtok(gfg, s);

    // Checks for delimiter
    while (tok != 0) {
        printf(" %s\n", tok);

        // Use of strtok
        // go through other tokens
        tok = strtok(0, s);
    }

    return (0);
}
```

输出:

```cpp
 Geeks
 for
 geeks
 Contribute
```

**实际应用**
strtok 可以基于一些分隔符将一个字符串拆分成多个字符串。一个**简单的 CSV 文件**支持可以使用这个功能来实现。CSV 文件以逗号作为分隔符。

## C

```cpp
// C code to demonstrate practical application of
// strtok
#include <stdio.h>
#include <string.h>

// Driver function
int main()
{
    // Declaration of string
    // Information to be converted into CSV file
    char gfg[100] = " 1997 Ford E350 ac 3000.00";

    // Declaration of delimiter
    const char s[4] = " ";
    char* tok;

    // Use of strtok
    // get first token
    tok = strtok(gfg, s);

    // Checks for delimiter
    while (tok != 0) {
        printf("%s, ", tok);

        // Use of strtok
        // go through other tokens
        tok = strtok(0, s);
    }

    return (0);
}
```

输出:

```cpp
1997, Ford, E350, ac, 3000.00,
```

**参考:**
1) [手册页 strtok _ r()](https://linux.die.net/man/3/strtok_r)T5】2)[http://stackoverflow . com/questions/15961253/c-correct-usage-of-strtok-r](http://stackoverflow.com/questions/15961253/c-correct-usage-of-strtok-r)
本文由 **MAZHAR IMAM KHAN** 和 [**shantanu_23**](https://auth.geeksforgeeks.org/profile.php?user=shantanu_23) 投稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。