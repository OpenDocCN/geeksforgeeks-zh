# C 程序输出|设置 66(访问内存位置)

> 原文:[https://www . geesforgeks . org/c 程序输出-set-66-访问内存-位置/](https://www.geeksforgeeks.org/output-of-c-programs-set-66-accessing-memory-locations/)

> **Q1。这段代码的输出是真还是假？**

```cpp
#include <stdio.h>
int main(void)
{
    int b = 20;
    int* y = &b;
    char n = 'A';
    char* z = &n;
    y[0] = z[0];
    printf((*y == *z) ? "True" : "False");
}
```

```cpp
A. True
B. False
C. Program would crash
D. Compilation error
```

**回答:**

```cpp
A. True
```

**说明:**
20 的二进制形式是 10100，存储在内存中。因为它是 int 类型，所以分配了四个字节，10100 存储在第 0 个位置。我们从左到右访问数组的元素。但是，在内存中，内存的位(根本不是数组)是从右向左访问的。ASCII 值存储在另一个只有第 0 个位置的 1 字节块中。当我们将 y[0]等同于 z[0]时，我们就间接覆盖了 b 的值。这使得两个指针相等。

> **Q2。这个程序的输出是什么？**

```cpp
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
    char x = 'A';
    char* y = (char*)malloc(sizeof(char));
    y = &x;
    for (int i = 0; i < 26; i++) {
        printf("%c", x);
        y[0] += 1;
    }
}
```

```cpp
A. SDKJNSDNSKDJNSKDVNSKJD
B. SLKFVMSLFKVSFLALKDJF
C. ABCDEFGHIJKLMNOPQRSTUVWXYZ
D. NONEOFTHEABOVE
```

**回答:**

```cpp
C. ABCDEFGHIJKLMNOPQRSTUVWXYZ
```

**解释:**
分配给一个字符的空间只有 1 字节或 8 位。y 是在运行时分配的。它包含 x 的地址。现在，我们可以索引 x 的内存位置。并且，对 y 的任何更改也会反映在 x 中。当执行 y[0]+=1 时，在每个循环中，该 1 字节数据的最后一位递增 1，如下所示:

```cpp
Initial:
00001010 (Binary form of 'A')

In loop
00001010 + 1 = 00001011 = B
00001011 + 1 = 00001100 = C
00001100 + 1 = 00001101 = D

and goes on up till Z.

```

注意:试图索引 y[1]和任何其他位置会给出一个垃圾值。

> **Q3。这个节目最后会印些什么？**

```cpp
#include <stdio.h>
int main(void)
{
    int a = 20, b = 10;
    int *x = &a, *y = &b;
    int c = y[0], d = x[0];
    x[0] = c;
    y[0] = d;
    printf("%d %d", *x, *y);
}
```

```cpp
A. 20 20
B. 20 10
C. 10 10
D. 10 20
```

**回答:**

```cpp
D. 10 20
```

**说明:**

这里，只有 a 和 b 的第 0 位被改变，导致值的改变。

> **Q4。程序结尾的 a 的值和开头的值一样吗？**

```cpp
#include <stdio.h>
int main(void)
{
    int a = 100;
    char* b = (char*)&a;
    b[0] += 132;
    b[1] += 3;
    b[0] = (232 - 32) / 2;
    b[1] *= 0;
    printf("%d\n", a);
}
```

```cpp
A. Yes
B. No
C. Program would crash
D. Compilation error
```

**回答:**

```cpp
A. Yes
```

**说明:**
100 的二进制值是 01100100，132 是 10000100，3 是 0000011。这就是发生的事情

```cpp
   b[3]     b[2]     b[1]     b[0]
 00000000 00000000 00000000 01100100
+00000000 00000000 00000011 10000100
------------------------------------
 00000000 00000000 00000011 11101000

This gives 1000.

```

现在这些值又被替换了。232-32 是 200，这个除以 2 得到 100，在 b[0]处被替换。所以，11101000 就变成了 01100100。b[1]*=0 使得 b[1]的所有 8 位都=0。这使得 a 的输出为 100，与开始时相同。

> **Q5。这个程序会怎么样？**

```cpp
#include <stdio.h>
struct A {
    int a;
} A1;
struct B {
    int b;
} B1;
int main(void)
{
    A1.a = 10;
    B1.b = 100;
    char* x = (char*)&A1;
    char* y = (char*)&B1;
    y = (char*)0x100;
    x[0] = y[1];
    printf("%d\n", A1.a);
    printf("%d", B1.b);
}
```

```cpp
A. Compilation error
B. Segmentation Fault
C. Output would be returned
D. None of the above
```

**回答:**

```cpp
B. Segmentation Fault
```

**解释:**
程序会崩溃，因为 y 指向 0x100，这是其他正在运行的程序的地址。

> **Q6。这个程序的输出是什么(把 x 的地址看作 62fe14)？**

```cpp
#include <stdio.h>
int main(void)
{
    int a = 100;
    char* x = (char*)&a;
    char** y = &x;
    y[0] = (char*)0x62fe14;
    printf("%x\n", x);
    printf("%x", *y);
}
```

```cpp
A. 0x0010
   0x1902
B. Crash
C. 0x62fe14
   0x62fe15
D. 0x62fe14
   0x62fe14
```

**回答:**

```cpp
D. 0x62fe14
   0x62fe14
```

**说明:**
y[0]已经包含 0x 62 fe14(x 的地址)。而*y 给出了 x 的地址，即 0x62fe14。执行 y[0]=(char *)0x62fe14 会替换该值，但不具有个人用途。如果您更改 0x62fe14 中的任何内容，不仅会影响 y[0]，还会更改 a 的地址，因为 y 的地址是 x，存储在第 0 个位置。

> **Q7。这个程序的输出是什么？**

```cpp
#include <stdio.h>
struct A {
    int a1;
    struct B {
        int a1;
    } A1;
} B1;
int main(void)
{
    B1.a1 = 10;
    B1.A1.a1 = 11;
    int* x = &B1.a1;
    int* y = &B1.A1.a1;
    x = y;
    char** z = (char**)&x;
    *z[0] = x[0];
    printf("%x", **z);
}
```

```cpp
A. a
B. b
C. ab
D. No output
```

**回答:**

```cpp
B. b
```

**说明:**
将 x 初始化为 y 会改变 x 持有的地址，基本上就是谋杀 B1.a1 的地址，用 y 中的值替换 x 中的值，即 11。*z[0] = x[0]没有用，因为它已经包含 x 的地址。打印 z 的十六进制值得到 b(十六进制为 11)。

> **Q8。印的是什么？**

```cpp
#include <stdio.h>
int main(void)
{
    int a = (int)0b01001011;
    int* b = &a;
    int n[10] = { (int)0b010110, 17,
                  -4, -13, 19, -19,
                  10, (int)0b11110110 };
    for (int i = 0; i < 9; i++) {
        printf("%c", b[0]);
        b[0] += n[i];
    }
}
```

```cpp
A. Karnataka
B. karnataka
C. Kerala
D. kerala
```

**回答:**

```cpp
A. Karnataka
```

**说明:**
01001011 的整数值为 75，ASCII 值为‘K’。010110 的整数值是 22，11110110 的整数值是-10。由于不超过 32 位(4 字节)，b[0]包含整个数字。将 n 的每个值相加，替换 b[0]中的值，导致打印每个字符(因为格式说明符)。

> **Q9。这个程序的输出是什么样的？**

```cpp
#include <stdio.h>
int main(void)
{
    // Use this as a reference:
    // 1011001100110011
    // 1111000011110011
    // 0111000011010011
    // 0011000000001001;
    int a = (int)0b1011001100110011111100001111001101110000110100110011000000001001;
    short int* b = (short int*)&a;
    printf("%d %d %d %d", b[3], b[2], b[1], b[0]);
}
```

```cpp
A. decimal value of 1011001100110011 decimal value of 1111000011110011 decimal value of 0111000011010011 decimal value of 0011000000001001
B. Junk value Junk value Junk value decimal value of 0011000000001001
C. Junk value Junk value Junk value Junk value
D. Junk value Junk value decimal value of 0111000011010011 decimal value of 0011000000001001
```

**回答:**

```cpp
D. Junk value Junk value decimal value of 0111000011010011 decimal value of 0011000000001001
```

**说明:**
短整型的大小是 2 字节，等于 16 位。a 只取这 64 位中的 32 位。b[0]存储 2 个字节，b[1]存储 2 个字节。这就是为什么你得到的输出有两个垃圾值和两个十进制值。

> **Q10。这个程序的输出是什么？**

```cpp
#include <stdio.h>
union A {
    int a;
    long long int b;
} A1;
int main(void)
{
    A1.a = 10;
    A1.b = 100;
    char* a = (char*)&A1;
    printf("%x %x %x %x %x %x %x %x",
           a[7], a[6], a[5],
           a[4], a[3], a[2],
           a[1], a[0]);
}
```

```cpp
A. 0 0 0 0 0 0 0 64
B. 0 0 0 0 0 0 0 0
C. All junk values
D. 0 0 0 0 0 0 0 A
```

**回答:**

```cpp
A. 0 0 0 0 0 0 0 64
```

**说明:**
这个并集的大小是 8 字节或者 64 位。输入到联合中的最新值是 100，它取代了最初有 10 的第一个位置。100 的十六进制值是 64，产生这个输出。7 字节为 0，1 字节为 64。