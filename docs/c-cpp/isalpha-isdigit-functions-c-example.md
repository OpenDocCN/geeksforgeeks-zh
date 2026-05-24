# isalpha()和 isdigit()函数用 cstring 举例说明。

> 原文:[https://www . geesforgeks . org/isalpha-isdigit-functions-c-example/](https://www.geeksforgeeks.org/isalpha-isdigit-functions-c-example/)

**isalpha(c)** 是 C 中的一个函数，可以用来检查传递的字符是否是字母表。如果是字母表，它返回非零值，否则返回 0。例如，它为“A”到“Z”和“A”到“Z”返回非零值，为其他字符返回零。
类似地，**是数字(c)** 是 C 中的一个函数，可以用来检查传递的字符是否是数字。如果是数字，则返回非零值，否则返回 0。例如，它为“0”到“9”返回非零值，为其他值返回零。
**避免常见错误:**需要注意的是，本文不涉及字符串！只有 Cstrings。Cstrings 是单个字符(char)的行为数组。这有好处也有坏处。
**例题:**给定一个 cstring **str** ，求该 cstring 中字母的个数和小数位数。
**示例:**

```cpp
Input: 12abc12
Output: Alphabetic_letters = 3, Decimal_digits = 4

Input: 123 GeeksForGeeks is Number 1
Output: Alphabetic_letters = 21, Decimal_digits = 4

```

**解释和方法:**

## C

```cpp
// C program to demonstrate working of isalpha() and
// isdigit().
#include <ctype.h>
#include <stdio.h>
#include <stdlib.h>

int main()
{
    char str[] = "12abc12";

    int alphabet = 0, number = 0, i;
    for (i = 0; str[i] != '\0'; i++)
    {

        // check for alphabets
        if (isalpha(str[i]) != 0)
            alphabet++ ;

        // check for decimal digits
        else if (isdigit(str[i]) != 0)
            number++ ;
    }

    printf("Alphabetic_letters = %d, "
           "Decimal_digits = %d\n",
           alphabet, number);

    return 0;
}
```

**输出:**

```cpp
Alphabetic_letters = 3, Decimal_digits = 4

```

本文由**马扎伊玛目汗**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。