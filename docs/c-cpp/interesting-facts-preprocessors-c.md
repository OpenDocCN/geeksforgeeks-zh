# C 语言中宏和预处理程序的有趣事实

> 原文:[https://www . geesforgeks . org/interest-facts-preprocessors-c/](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/)

在 C 程序中，所有以 **#** 开头的行都由预处理器处理，预处理器是编译器调用的特殊程序。这里我们的意思是说‘#’符号比程序中的其他语句更先用于处理功能，也就是说，它在运行前或编译时处理一些代码。用一个非常基本的术语来说，预处理器拿走一个 C 程序，产生另一个没有任何 **#** 的 C 程序。

下面是一些关于 c 语言中预处理程序的有趣事实。

**1)** 当我们使用 ***include*** 指令时，包含的头文件内容(经过预处理)被复制到当前文件中。
角括号**<****>**指示预处理器查看保存所有头文件的标准文件夹。双引号****指示预处理器查找当前文件夹(当前目录)。****

******2)** 当我们使用 ***为一个常量定义*** 时，预处理器产生一个 C 程序，在该程序中搜索定义的常量并用给定的表达式替换匹配的标记。例如在下面的程序中 *max* 被定义为 100。****

## ****C****

```cpp
**#include <stdio.h>
#define max 100
int main()
{
    printf("max is %d", max);
    return 0;
}**
```

******Output:** 

```cpp
max is 100
```**** 

******3)** 宏可以像参数一样工作，不检查参数的数据类型。例如，以下宏 INVENTION(x)可用于任何数据类型的 x。****

## ****C****

```cpp
**#include <stdio.h>
#define INCREMENT(x) ++ x
int main()
{
    char* ptr = "GeeksQuiz";
    int x = 10;
    printf("%s  ", INCREMENT(ptr));
    printf("%d", INCREMENT(x));
    return 0;
}**
```

******Output:** 

```cpp
eeksQuiz  11
```**** 

******4)** 宏展开前不计算宏参数。例如，考虑以下程序****

## ****C****

```cpp
**#include <stdio.h>
#define MULTIPLY(a, b) a* b
int main()
{
    // The macro is expanded as 2 + 3 * 3 + 5, not as 5*8
    printf("%d", MULTIPLY(2 + 3, 3 + 5));
    return 0;
}
// Output: 16**
```

******Output:** 

```cpp
16
```**** 

****前面的问题可以用下面的程序解决****

## ****C****

```cpp
**#include <stdio.h>
// here, instead of writing a*a we write (a)*(b)
#define MULTIPLY(a, b) (a) * (b)
int main()
{
    // The macro is expanded as (2 + 3) * (3 + 5), as 5*8
    printf("%d", MULTIPLY(2 + 3, 3 + 5));
    return 0;
}
// This code is contributed by Santanu**
```

******Output:** 

```cpp
40
```**** 

******5)** 传递给宏的令牌可以使用名为“令牌粘贴”操作符的操作符 **##** 进行连接。****

## ****C****

```cpp
**#include <stdio.h>
#define merge(a, b) a##b
int main() { printf("%d ", merge(12, 34)); }**
```

******Output:** 

```cpp
1234
```**** 

******6)** 传递给宏的标记可以通过在它之前使用#转换为字符串。****

## ****C****

```cpp
**#include <stdio.h>
#define get(a) #a
int main()
{
    // GeeksQuiz is changed to "GeeksQuiz"
    printf("%s", get(GeeksQuiz));
}**
```

******Output:** 

```cpp
GeeksQuiz
```**** 

******7)** 可以使用“\”将宏写入多行。最后一行不需要有“\”。****

## ****C****

```cpp
**#include <stdio.h>
#define PRINT(i, limit)                                    \
    while (i < limit) {                                    \
        printf("GeeksQuiz ");                              \
        i++ ;                                               \
    }
int main()
{
    int i = 0;
    PRINT(i, 3);
    return 0;
}**
```

******Output:** 

```cpp
GeeksQuiz GeeksQuiz GeeksQuiz
```**** 

******8)** 带有参数的宏应该避免，因为它们有时会引起问题。内联函数应该是首选的，因为内联函数中有类型检查参数计算。从 [C99](http://en.wikipedia.org/wiki/C99) 开始，C 语言也支持内联函数。****

****例如，考虑以下程序。从第一眼看，输出似乎是 1，但它产生 36 作为输出。****

## ****C****

```cpp
**#include <stdio.h>

#define square(x) x* x
int main()
{
    // Expanded as 36/6*6
    int x = 36 / square(6);
    printf("%d", x);
    return 0;
}**
```

******Output**

```cpp
36
```**** 

****但是我们可以按如下方式编写这段代码，以获得预期的结果，即 1:****

## ****C****

```cpp
**#include <stdio.h>

#define square(x) (x * x)
int main()
{
    // Expanded as 36/(6*6)
    int x = 36 / square(6);
    printf("%d", x);
    return 0;
}**
```

******输出******

******1******

****如果我们使用内联函数，我们会得到预期的输出。此外，上面第 4 点中给出的程序可以使用内联函数进行修正。****

## ****C****

```cpp
**#include <stdio.h>

static inline int square(int x) { return x * x; }
int main()
{
    int x = 36 / square(6);
    printf("%d", x);
    return 0;
}**
```

******Output:** 

```cpp
1
```**** 

******9)** 预处理程序还支持 if-else 指令，这些指令通常用于条件编译。****

## ****C****

```cpp
**int main()
{
#if VERBOSE >= 2
    printf("Trace Message");
#endif
}**
```

******Output:** 

```cpp
No Output
```**** 

******10)** 头文件可能被直接或间接包含多次，这导致了相同变量/函数的重新声明问题。为了避免这个问题，使用了类似*****ifdef***和 ***ifndef*** 的指令。******

******11)** 有一些标准宏可以用来打印程序文件(__FILE__)、编译日期(__DATE__)、编译时间(__TIME__)和 C 代码中的行号(__LINE__)****

## ****C****

```cpp
**#include <stdio.h>

int main()
{
    printf("Current File :%s\n", __FILE__);
    printf("Current Date :%s\n", __DATE__);
    printf("Current Time :%s\n", __TIME__);
    printf("Line Number :%d\n", __LINE__);
    return 0;
}**
```

******Output:** 

```cpp
Current File :/usr/share/IDE_PROGRAMS/C/other/081c548d50135ed88cfa0296159b05ca/081c548d50135ed88cfa0296159b05ca.c
Current Date :Sep  4 2019
Current Time :10:17:43
Line Number :8
```**** 

******12)** 我们可以使用:
**# unde MACRO _ NAME**删除已经定义的宏****

## ****C****

```cpp
**#include <stdio.h>
#define LIMIT 100
int main()
{
    printf("%d", LIMIT);
// removing defined macro LIMIT
#undef LIMIT
    // Next line causes error as LIMIT is not defined
    printf("%d", LIMIT);
    return 0;
}
// This code is contributed by Santanu**
```

****以下程序正确执行，因为我们在删除了之前定义的宏 LIMIT 后，将 LIMIT 声明为整数变量****

## ****C****

```cpp
**#include <stdio.h>
#define LIMIT 1000
int main()
{
    printf("%d", LIMIT);
// removing defined macro LIMIT
#undef LIMIT
    // Declare LIMIT as integer again
    int LIMIT = 1001;
    printf("\n%d", LIMIT);
    return 0;
}**
```

******Output:** 

```cpp
1000
1001
```**** 

****关于宏使用的另一个有趣的事实(**# unde**)****

## ****C****

```cpp
**#include <stdio.h>
// div function prototype
float div(float, float);
#define div(x, y) x / y

int main()
{
    // use of macro div
    // Note: %0.2f for taking two decimal value after point
    printf("%0.2f", div(10.0, 5.0));
// removing defined macro div
#undef div
    // function div is called as macro definition is removed
    printf("\n%0.2f", div(10.0, 5.0));
    return 0;
}

// div function definition
float div(float x, float y) { return y / x; }
// This code is contributed by Santanu**
```

******Output:** 

```cpp
2.00
0.50
```**** 

****你可能想参加一个关于 C
中宏和预处理程序的[测验。如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的主题的信息。](http://geeksquiz.com/c-language/macro-preprocessor/)****