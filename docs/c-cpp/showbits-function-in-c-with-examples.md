# 用例子展示 C 中的( )函数

> 原文:[https://www . geeksforgeeks . org/show bits-function-in-c-with-examples/](https://www.geeksforgeeks.org/showbits-function-in-c-with-examples/)

[按位运算符](https://www.geeksforgeeks.org/interesting-facts-bitwise-operators-c/)是运算符(就像+、*、& &等)。)在二进制级别对整数和单位进行操作。这意味着他们直接看二进制数字或整数位。这听起来很可怕，但事实上，按位运算符非常容易使用，也非常有用！不过，重要的是你要了解二进制数和十六进制数。

### 按位运算符

我们来看看不同的按位运算符:

1.  & (bitwise AND)
2.  | (bitwise OR)
3.  ~ (bitwise NOT)
4.  (bitwise xor)
5.  < t30] (shift left by bit)
6.  > > (right shift by bit)
7.  > > > (bit-wise unsigned right shift)
8.  & = (bitwise AND)
9.  > > = (right shift and assignment by bit)
10.  > > > = (bit-wise unsigned right shift and assignment)

本文的重点是 showbits() [功能](https://www.geeksforgeeks.org/builtin-functions-gcc-compiler/)。让我们看看它与按位运算符的关系。

### 显示位( )函数

这个函数主要处理按位运算符的概念。让我们来看看下面的 C 程序，了解 showbits()函数。

## C

```cpp
// C program to demonstrate the
// showbits() function
#include <stdio.h>
void showbits (int n)
{
  int i, k, andmask;

  for (i = 15; i >= 0;i--)
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

**Output**

```cpp
0000000000000101
```

**解释**

1.  All you do in this function is use an AND operator and a variable **and an AND.** The andmask variable is used to check the status of each bit. If this bit is off, 0 is printed; otherwise, 1 is printed.
2.  The first pass through the loop, the variables **and** will contain the value of 100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
3.  If the most significant bit of the variable n is 0, then k will contain a value of 0; otherwise, it will contain a non-zero value.
4.  If k contains 0, then printf () will print 0; otherwise, it will print 1.
5.  In the second cycle of the cycle, the value of I decreases, so the values of **and** change, and now it will be 10000000000000000000000000000000, which will check that the next most significant bit is 1\. Repeat the same operation for all bits in the number.

如果需要十进制数的二进制，那么基本上所有的整数在计算机中都是二进制的。只是当使用 printf 和“%d”打印时，它变成了该值的十进制表示形式的字符串。如果需要其他基数(如基数 2 或二进制)的结果，请提供正确的 printf 格式字符串(如十六进制的“%x”)，或者只构建该字符串并将其打印出来。

下面是可以在[2，36]中以任意基数构建整数的字符串表示形式的代码。

T3】CT5

```cpp
// C program to implement the
// above approach
#include <stdio.h>
#include <string.h>

char digits[] =
     "01234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ";

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

T6T8**输出**T1

**说明:**函数 base_change()显示任意整数或字符值的二进制表示。现在，只要知道 base_change()函数显示整数的二进制等价物就足够了。