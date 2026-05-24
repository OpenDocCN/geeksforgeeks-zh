# C/c++

中 printf()和 scanf()的返回值

> 原文:[https://www . geesforgeks . org/return-values-of-printf-and-scanf-in-c-CPP/](https://www.geeksforgeeks.org/return-values-of-printf-and-scanf-in-c-cpp/)

**printf()** 和 **scanf()函数返回什么值？**

**printf() :** 返回**打印字符总数**，如果输出错误或编码错误
则返回负值**例 1:** 下面代码中的 printf()函数返回 6。因为“CODING”包含 6 个字符。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C/C++ program to demonstrate return value
// of printf()
#include <stdio.h>

int main()
{
    char st[] = "CODING";

    printf("While printing ");
    printf(", the value returned by printf() is : %d",
                                    printf("%s", st));

    return 0;
}
```

**Output**

```cpp
While printing CODING, the value returned by printf() is : 6
```

**示例 2:** 下面编写的代码中的 printf()函数返回 9。As '123456789 '包含 9 个字符。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C/C++ program to demonstrate return value
// of printf()

#include <stdio.h>
int main()
{
    long int n = 123456789;

    printf("While printing ");
    printf(", the value returned by printf() is : %d",
                                    printf("%ld", n));

    return 0;
}
```

**Output**

```cpp
While printing 123456789, the value returned by printf() is : 9
```

**scanf() :** 它返回**成功扫描的输入总数**，如果在分配第一个接收参数之前输入失败，则返回 EOF。
**例 1:** 下面代码中的第一个 scanf()函数返回 1，因为它正在扫描 1 个项目。类似地，第二个 scanf()在扫描 2 个输入时返回 2，第三个 scanf()在扫描 3 个输入时返回 3。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C/C++ program to demonstrate return value
// of printf()

#include <stdio.h>
int main()
{
    char a[100], b[100], c[100];

    // scanf() with one input
    printf("\n First scanf() returns : %d",
                            scanf("%s", a));

    // scanf() with two inputs
    printf("\n Second scanf() returns : %d",
                       scanf("%s%s", a, b));

    // scanf() with three inputs
    printf("\n Third scanf() returns : %d",
                  scanf("%s%s%s", a, b, c));

    return 0;
}
```

```cpp
Input:
Hey!
welcome to
geeks for geeks

Output:
 First scanf() returns : 1
 Second scanf() returns : 2
 Third scanf() returns : 3
```