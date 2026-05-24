# 用例子展示 C 中的 `showbits()` 函数

> 原文: [https://www.geeksforgeeks.org/showbits-function-in-c-with-examples/](https://www.geeksforgeeks.org/showbits-function-in-c-with-examples/)

[按位运算符](https://www.geeksforgeeks.org/interesting-facts-bitwise-operators-c/)是运算符（就像 `+`、`*`、`&&` 等）在二进制级别对整数和位进行操作。这意味着它们直接看二进制数字或整数位。这听起来很可怕，但事实上，按位运算符非常容易使用，也非常有用！不过，重要的是你要了解二进制数和十六进制数。

## 按位运算符

我们来看看不同的按位运算符：

1.  `&` (bitwise AND)
2.  `|` (bitwise OR)
3.  `~` (bitwise NOT)
4.  `^` (bitwise xor)
5.  `<<` (shift left by bit)
6.  `>>` (right shift by bit)
7.  `>>>` (bit-wise unsigned right shift)
8.  `&=` (bitwise AND)
9.  `>>=` (right shift and assignment by bit)
10. `>>>=` (bit-wise unsigned right shift and assignment)

本文的重点是 `showbits()` [函数](https://www.geeksforgeeks.org/builtin-functions-gcc-compiler/)。让我们看看它与按位运算符的关系。

## `showbits()` 函数

这个函数主要处理按位运算符的概念。让我们来看看下面的 C 程序，了解 `showbits()` 函数。

### C 程序示例

```cpp
// C program to demonstrate the
// showbits() function
#include <stdio.h>
void showbits (int n)
{
  int i, k, andmask;

  for (i = 15; i >= 0; i--)
  {
    andmask = 1 << i;
    k = n & andmask;
    k == 0 ? printf ("0") : printf ("1");
  }
}

// Driver code
int main()
{
  showbits(5);
  return 0;
}
```

**输出**

```cpp

```

**解释**

1.  在这个函数中，你所做的就是使用一个 `AND` 运算符和一个变量 `andmask`。`andmask` 变量用于检查每个位的状态。如果这个位是关闭的，就打印 0；否则，打印 1。
2.  第一次循环时，变量 `andmask` 将包含值 `1000000000000000`。
3.  如果变量 `n` 的最高有效位是 0，那么 `k` 将包含值 0；否则，它将包含一个非零值。
4.  如果 `k` 包含 0，那么 `printf()` 将打印 0；否则，它将打印 1。
5.  在第二次循环中，`i` 的值减小，因此 `andmask` 的值改变，现在它将是 `0100000000000000`，这将检查下一个最高有效位是 1 还是 0。对数字中的所有位重复相同的操作。

如果需要十进制数的二进制，那么基本上所有的整数在计算机中都是二进制的。只是当使用 `printf` 和 `%d` 打印时，它变成了该值的十进制表示形式的字符串。如果需要其他基数（如基数 2 或二进制）的结果，请提供正确的 `printf` 格式字符串（如十六进制的 `%x`），或者只构建该字符串并将其打印出来。

下面是可以在 [2，36] 中以任意基数构建整数的字符串表示形式的代码。

### C 程序示例

```cpp
// C program to implement the
// above approach
#include <stdio.h>
#include <string.h>

char digits[] =
     "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ";

void reverse(char* start, char* end)
{
  for(end--; start < end; start++, end--)
  {
    char t = *start;
    *start = *end;
    *end = t;
  }
}

int base_change(int n,
                int base, char* buffer)
{
  int pos = 0;

  if (base > strlen(digits))
    return -1;
  while(n)
  {
    buffer[pos] = digits[n % base];
    n /= base;
    pos++ ;
  }

  buffer[pos] = '\0';
  reverse(buffer, buffer + pos);
  return 0;
}

// Driver code
int main()
{
  char buffer[32];
  int conv = base_change(1024,
                         2, buffer);
  if (conv == 0)
    printf("%s\n", buffer);
  return 0;
}
```

**输出**

**说明：** 函数 `base_change()` 显示任意整数或字符值的二进制表示。现在，只要知道 `base_change()` 函数显示整数的二进制等价物就足够了。