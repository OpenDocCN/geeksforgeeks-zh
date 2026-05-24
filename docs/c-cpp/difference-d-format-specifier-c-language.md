# C 语言中%d 和%i 格式说明符的区别

> 原文:[https://www . geesforgeks . org/difference-d-format-说明符-c-language/](https://www.geeksforgeeks.org/difference-d-format-specifier-c-language/)

格式说明符是由表示格式说明符的初始百分比符号(%)构成的序列，格式说明符用于指定要从流中检索并存储到附加参数所指向的位置的数据的类型和格式。简而言之，它告诉我们存储哪种类型的数据和打印哪种类型的数据。
**例如**–如果我们要使用 scanf()和 printf()函数读取和打印整数，则使用%i 或%d，但在 **%i** 和 **%d** 格式说明符中有细微的区别。

> %d 指定有符号的十进制整数，而%i 指定整数。

**%d 和%i 的行为与 printf** 相似

printf 的%i 和%d 格式说明符没有区别。考虑下面的例子。

## C

```cpp
// C program to demonstrate
// the behavior of %i and %d
// with printf statement
#include <stdio.h>

int main()
{
    int num = 9;

    // print value using %d
    printf("Value of num using %%d is = %d\n", num);

    // print value using %i
    printf("Value of num using %%i is = %i\n", num);

    return 0;
}
```

```cpp
Output:
Value of num using %d is = 9
Value of num using %i is = 9
```

**%d 和%i 行为在 scanf** 中不同

**%d 假设基数为 10，而%i 自动检测基数**。因此，当两个说明符与输入说明符一起使用时，它们的行为不同。所以，012 是 10% I，12% d。

*   **%d** 取整数值为带符号的十进制整数，即取正值和负值，但数值应为十进制，否则会打印垃圾值。(注意:如果输入是八进制格式，如:012，则%d 将忽略 0，并将输入视为 12)考虑以下示例。

*   **%i** 取整数值为十进制、十六进制或八进制类型的整数值。
    以十六进制格式输入值–值应在“0x”之前提供，以八进制格式输入值–值应在“0”之前提供。

考虑下面的例子。

## C

```cpp
// C program to demonstrate the difference
// between %i and %d specifier
#include <stdio.h>

int main()
{
    int a, b, c;

    printf("Enter value of a in decimal format:");
    scanf("%d", &a);

    printf("Enter value of b in octal format: ");
    scanf("%i", &b);

    printf("Enter value of c in hexadecimal format: ");
    scanf("%i", &c);

    printf("a = %i, b = %i, c = %i", a, b, c);

    return 0;
}
```

```cpp
Output:
Enter value of a in decimal format:12
Enter value of b in octal format: 012
Enter value of c in hexadecimal format: 0x12
a = 12, b = 10, c = 18
```

**说明:**
a as 12 的十进制值为 12
b as 12 的十进制值为 10
c as 12 的十进制值为 18
本文由 [Shubham Bansal](https://www.quora.com/profile/Shubham-Bansal-209) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。