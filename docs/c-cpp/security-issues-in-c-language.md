# C 语言中的安全问题

> 原文:[https://www . geesforgeks . org/security-issues-in-c-language/](https://www.geeksforgeeks.org/security-issues-in-c-language/)

[C](https://www.geeksforgeeks.org/c-language-set-1-introduction/) 是一种非常强大且流行的[编程语言](https://www.geeksforgeeks.org/c/)。它最早是在 20 世纪 70 年代开发的。c 语言用于编程网络驱动程序、解释程序和编译器等。
尽管 C 语言在不同的系统中被广泛使用，但它仍然有许多与之相关的安全缺陷。本文主要讨论 C 语言中的安全漏洞。这些安全问题主要与易受攻击的库函数、数组和指针的无边界检查有关。

**易受攻击的库函数:**
CWE 代码:[CWE–242](https://cwe.mitre.org/data/definitions/242.html)、[CWE–120](https://cwe.mitre.org/data/definitions/120.html)、 [CWE-77](https://cwe.mitre.org/data/definitions/77.html)

**1。缓冲区和内存相关:**

**a .**[**get()**](https://www.geeksforgeeks.org/gets-is-risky-to-use/)**:**这个函数是 C 语言标准输入输出库的一部分。它不检查缓冲区大小，恶意输入很容易导致缓冲区溢出。
下面是演示上述概念的 C 程序-

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>

// Driver code
int main()
{
    char buf[24];
    printf("Please enter your name and press <Enter>\n");
    gets(buf);
    printf("%s", buf);
    return 0;
}
```

**警告:**

> prog.c:在函数“main”中:
> prog.c:10:1:警告:函数“gots”
> 的隐式声明[-Wiplicit-function-declaration]
> gots(buf)；
> ^
> /tmp/ccmwzcq . o:在功能` main ':
> 69c 380139 e 12 dbab 30 e 0550 af 51 F5 a9 . c:(。text+0x2e):警告:` get '
> 功能有危险，不应使用。

**输出:**

> 输入:
> 极客头像
> 输出:
> 请输入您的姓名并按
> 极客头像

**解释:**
在上面的代码中，攻击者可以给出大块数据作为输入，get()函数会试图将所有这些数据存储到缓冲区中，而不考虑缓冲区的大小，这最终会导致缓冲区溢出的情况，从而进一步导致任意代码执行、信息泄露。

**缓解:**
用 get()函数解决这个问题。程序员可以使用 [fgets()](https://www.geeksforgeeks.org/fgets-gets-c-language/) 功能。它根据缓冲区大小限制输入长度。
下面是实现上述方法的 C 程序-

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>
#define MAX 15

// Driver code
int main()
{
    char buf[MAX];
    fgets(buf, MAX, stdin);
    printf("%s", buf);
    return 0;
}
```

**输出:**

> 输入:极客暴发户
> 输出:极客暴发户

**解释:**
在上面的代码中，fgets()函数是以缓冲区大小‘MAX’为参数的，它只会将可以安全存储的数据写入该大小的缓冲区，而不会溢出。

**b .**[**strcpy()**](https://www.geeksforgeeks.org/strcpy-in-c-cpp/)**:**这个内置函数也不检查缓冲区长度，可以根据恶意输入覆盖内存位置。如果目标字符串的缓冲区大小大于 src 字符串，则将 src 字符串复制到带有终止空字符的目标字符串。但是如果目的缓冲区较少，那么 src 将复制内容而不终止空字符。字符串不能重叠，目标字符串必须足够大才能接收副本。
下面是演示上述概念的 C 程序-

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>
#include <string.h>

// Driver code
int main()
{
    char str1[2];
    char str2[] = "GeeksforGeeks";
    strcpy(str1, str2);
    printf("Copied string is: %s\n", str1);
    return 0;
}
```

**输出:**

> 输入:
> 极客头像
> 输出:
> 复制的字符串是:极客头像

**解释:**
在上面的代码中，strcpy()函数试图将 str2[]上可用的字符串复制到 str1[]上，而 str 1[]的缓冲区中没有足够的空间来处理该字符串，这将最终导致应用程序中的缓冲区溢出。

**缓解:**
使用 strncpy()函数代替 strcpy()。strncpy()根据可用的缓冲区大小限制输入的长度。
下面是演示上述概念的 C 程序-

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>
#include <string.h>
#define BUFFER_SIZE 24

// Driver code
int main()
{
    // 24 is the buffer size
    char str1[BUFFER_SIZE];
    char str2[] = "GeeksforGeeks";

    // Limits number of characters
    // to be copied
    strncpy(str1, str2, BUFFER_SIZE);
    printf("Copied string is: %s\n", str1);
    return 0;
}
```

**输出:**

> 输入:
> 极客头像
> 输出:
> 复制的字符串是:极客头像

**说明:**
在上面的代码中，strncpy()函数是以 BUFFER_SIZE 为参数的，它只会将可以安全存储的数据写入到 str1[ ]中，而不会溢出缓冲区。使用 strcpy()函数将一个大的字符数组复制到一个小的数组中是危险的，但是如果字符串适合，那么就不值得冒这个风险。如果目标字符串不足以存储源字符串，那么 strcpy()的行为是未指定或未定义的。

**注意:**
具有相同类型漏洞的其他库函数- [calloc](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/) 、malloc、 [realloc](https://www.geeksforgeeks.org/g-fact-66/) 、 [strcat](https://www.geeksforgeeks.org/strcat-vs-strncat-c/) 、 [memcpy](https://www.geeksforgeeks.org/memcpy-in-cc/) 。

**2。命令执行漏洞:**
如果攻击者可以控制命令文本或外部函数调用的参数，那么他可以非常容易地运行任意代码。
下面是演示上述概念的 C 程序-

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

// Driver code
int main()
{
    char str[40];
    fgets(str, 39, stdin);
    system(str);
    printf("%s", str);
}
```

**运行时错误:**

> sh:1:geesforgeks:找不到

**输出:**

> 输入:
> 极客头像
> 输出:
> 极客头像

**解释:**
在上面的代码中，如果 str 被攻击者控制，那么他可以对系统执行任何命令，并且可以将整个系统置于危险之中。观察到的简历为 CVE-1999-0067，CVE-2019-12921。

**缓解:**

*   确保从程序调用的所有外部命令都是静态创建的。
*   使用库调用而不是外部进程来重新创建所需的功能。

**注意:**
同类型漏洞的其他库函数: [execl](https://www.geeksforgeeks.org/exec-family-of-functions-in-c/) 、execl、popen。

**3。格式字符串漏洞:**
[像%d、%s 这样的格式说明符如果在代码中使用不当，可能会让攻击者获得执行任意代码的权限，信息泄露，还可以完全控制应用程序。如果成功，它返回写入的字符总数，不包括字符串中附加的空字符，如果失败，则返回负数。
下面是演示上述概念的 C 程序-](https://www.geeksforgeeks.org/format-specifiers-in-c/)

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>

// Driver code
int main()
{
    char str[5];
    sprintf(str, "%s",
            "GGGGGGGGGGGGGG");
    printf("%s", str);
}
```

**运行时错误:**

> 来自中止(3)的中止信号(SIGABRT)

**解释:**
在上面这段代码中，格式说明符为%s 的 [sprintf](https://www.geeksforgeeks.org/sprintf-in-c/) 函数可能会导致缓冲区溢出，因为输出大小为 15，比接收到的大小仅为 5 的缓冲区大。
除此之外，str[ ]也可以由外部代理控制，并导致上述所有漏洞([CWE–13](https://cwe.mitre.org/data/definitions/134.html))。观察到的简历有 CVE-2001-0717、CVE-2002-1788、CVE-2006-2480 等。

**缓解:**

*   选择一种语言不会有这样的缺陷。
*   确保所有格式字符串函数都被传递了一个用户无法控制的静态字符串。
*   在格式字符串中使用不支持%n 运算符的函数。

**注意:**
具有相同类型漏洞的其他库函数: [fprintf](https://www.geeksforgeeks.org/fprintf-in-c/) 、 [printf](https://www.geeksforgeeks.org/return-values-of-printf-and-scanf-in-c-cpp/) 、 [sprintf](https://www.geeksforgeeks.org/sprintf-in-c/) 、 [snprintf](https://www.geeksforgeeks.org/snprintf-c-library/) 。

**指针的概念:**
[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)的概念导致了 C 编程语言的多个安全问题。

**1。空指针取消引用:** CWE 代码: [CWE-476](https://cwe.mitre.org/data/definitions/476.html) 。如果程序取消引用一个预期有效但结果为空的指针，那么它会导致程序崩溃，退出。缓解方法是在执行任何操作之前检查空指针。观察到的简历有 CVE-2005-3274、CVE-2005-1912、CVE-2004-0079 等。
下面是演示上述概念的 C 程序——

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>

// Driver code
int main()
{
    int val = 1;
    int* p = NULL;
    *p = val;
    printf("%d", *p);
    return 0;
}
```

**运行时错误:**

> 分段故障

**解释:**
在这段代码中，*p 是一个 NULL 指针，这意味着它没有指向内存位置，试图取消引用它会导致程序中出现意外行为或分段错误。

**缓解:**
下面是 C 程序，演示上述问题的缓解策略-

## C

```cpp
// C program to implement
// the above concept
#include <stdio.h>

// Driver code
int main()
{
    int val = 1;
    int* p = NULL;
    if (p == NULL) {
        printf("Pointer is NULL");
    }
    else {
        *p = val;
        printf("%d", *p);
    }
    return 0;
}
```

**输出:**

> 指针为空

**解释:**
在这段代码中，在对指针进行任何操作之前，首先对[空指针](https://www.geeksforgeeks.org/few-bytes-on-null-pointer-in-c/)进行检查。以下是 if 语句检查空条件，如果发现为真，则不执行进一步的操作。

**2。空闲后使用(通常称为悬空指针):** CWE 代码: [CWE-416](https://cwe.mitre.org/data/definitions/416.html) 。如果一个引用内存被释放，然后试图再次释放它，那么就会导致这种情况。它会导致程序崩溃、信息泄露和数据损坏。观察到的简历有 CVE-2010-4168、CVE-2010-2941、CVE-2010-2547 等。
下面是演示上述概念的 C 程序——

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>
int* fun()
{
    int y = 10;
    return &y;
}

// Driver code
int main()
{
    int* p = fun();
    printf("%d", *p);
    return 0;
}
```

**输出:**

> 分段故障

**解释:**
在上面的代码中，main()函数的*p 包含 fun()的返回值。通过 fun()的调用，控件移动到 int *fun()的上下文中，fun()返回“y”变量的地址，但是在 main()的上下文中，“y”在程序流返回后不再可用。因此，可以说*p 是一个[悬空指针](https://www.geeksforgeeks.org/dangling-void-null-wild-pointers/)，因为它指向未分配的内存。

**缓解:**
释放指针后将其设置为空。下面是演示上述概念的 C 程序——

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>
#include <stdlib.h>

// Driver code
int main()
{
    int n = 5;
    int* ptr;
    ptr = (int*)malloc(n * sizeof(int));

    // Memory has been successfully allocated
    printf("Memory successfully allocated using malloc.\n");

    // Free the memory
    free(ptr);
    printf("Malloc Memory successfully freed.\n");

    // freed pointer set to NULL value
    ptr = NULL;

    return 0;
}
```

**输出:**

> 使用 malloc 成功分配内存。
> Malloc 内存成功释放。

**解释:**
在上面这段代码中，在自由(ptr)操作之后，ptr 指针值被设置为 NULL，这将减少悬空指针的机会。

**数组无边界检查:**

**1。越界写入:** CWE 代码: [CWE-787](https://cwe.mitre.org/data/definitions/787.html) 在这种情况下，软件在预期的缓冲区之前或之后写入数据。它可能会导致未授权代码的执行、崩溃和重启。观察到的简历有 CVE-2020-0022、CVE-2009-0269、CVE-2009-1532 等。
下面是演示上述概念的 C 程序——

## C

```cpp
// Program to demonstrate
// accessing array out of bounds
#include <stdio.h>
int main()
{
    int arr[] = { 1, 2, 3, 4, 5 };
    printf("arr [0] is %d\n", arr[0]);
    printf("arr[10] is %d\n", arr[10]);

    // allocation memory to out of bound
    // element
    arr[10] = 11;
    printf("arr[10] is %d\n", arr[10]);
    return 0;
}
```

**运行时错误:**

> 分段故障

**解释:**
在上面这段代码中，数组有有效的索引 0、1、2、3 和 4，但是试图将值写入 arr[10]。由于 C 编译器不会检查数组边界，所以它会在预期的缓冲区之后写入数据。但是当试图打印索引 10 处的值时，它会显示一个错误。

**缓解:**

*   始终确保缓冲区足够大。
*   用于接受输入的函数应该有一个缓冲区限制实现。

下面是演示上述概念的 C 程序——

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>
int arr[5];

// Driver code
int main()
{
    int size = sizeof(arr) / sizeof(arr[0]);

    for (int i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }

    // Print elements of array
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    return 0;
}
```

**输出:**

> 输入:1 2 3 4 5 6 7 8 9 10
> 输出:1 2 3 4 5

**说明:**
在上面的代码中， [sizeof 运算符](https://www.geeksforgeeks.org/sizeof-operator-c/)被用来确定数组的大小，这样就可以得到索引的有效范围。sizeof(arr)将给出数组的整个大小，sizeof(arr[0])将给出一个元素的大小，因此使用除法运算，可以很容易地找到数组中的元素数量以及索引的范围。

**2。界外读数:** CWE 代码: [CWE-125](https://cwe.mitre.org/data/definitions/125.html) 。在这种情况下，软件在预期的缓冲区之前或之后读取数据。攻击者可能利用这一点从其他内存位置读取敏感信息，或者可能导致崩溃。观察到的简历有 CVE-2014-0160、CVE-2009-2523、CVE-2004-0184 等。
下面是演示上述概念的 C 程序——

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>
int getValueFromArray(int* arr,
                      int size,
                      int index)
{
    int value = -1;

    // only maximum limit is there
    if (index < size) {
        value = arr[index];
    }
    return value;
}

// Driver code
int main()
{
    int arrtest[] = { 1, 2, 3, 4, 5 };
    int j = getValueFromArray(arrtest, 5, -1);
    printf("%d", j);
    return 0;
}
```

**输出:**

> Zero

**解释:**
在上面这段代码中，函数内的 if 语句只检查索引值是否小于数组的大小。攻击者可能会给出一个负值作为索引，即使该值无效，读取操作仍将执行，这将最终导致读取非预期的数据。

**缓解:**

*   输入验证。
*   确保验证参数长度、缓冲区大小等的正确计算。

下面是演示上述概念的 C 程序——

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>
int getValueFromArray(int* arr,
                      int size,
                      int index)
{
    int value = -1;

    // only maximum limit and minimum
    // limit is there
    if (index >= 0 && index < size) {
        value = arr[index];
    }
    return value;
}

// Driver code
int main()
{
    int arrtest[] = { 1, 2, 3, 4, 5 };
    int j = getValueFromArray(arrtest, 5, -1);
    printf("%d", j);
    return 0;
}
```

**输出:**

> -1

**说明:**
在此代码中，最大和最小索引范围都在 if 语句中检查。如果攻击者试图给出无效的索引，则不会执行读取操作。