# C 编程中关键字长的工作

> 原文:[https://www . geesforgeks . org/work-of-keyword-long-in-c-programming/](https://www.geeksforgeeks.org/working-of-keyword-long-in-c-programming/)

![](img/760991b8d2dbaa2f6d87d22660ed759f.png)

**long** 是 Java 中的一个关键字，它象征着 [Long 数据类型](https://www.geeksforgeeks.org/java-lang-long-class-in-java/)。长数据类型是 64 位二进制补码整数，具有:

*   尺寸:64 位
*   数值:-2 <sup>63</sup> 至 2 <sup>63</sup> -1。

64 位 GCC 编译器的输出给出的长度为 8，而 32 位 GCC 编译器的长度为 4。所以每个编译器都不一样。现在的问题是这里到底发生了什么？让我们以编译器如何在内部分配内存的方式来讨论它。

中央处理器通过给内存地址寄存器地址从内存中调用数据。找到该位置，并将数据传输到内存数据寄存器。该数据被记录在处理器的一个寄存器中，以供进一步处理。这就是为什么数据总线的大小决定了处理器中寄存器的大小。现在，一个 32 位寄存器一次只能调用 4 字节大小的数据。如果数据大小超过 32 位，则需要两个周期的提取才能将数据放入其中。与 64 位相比，这降低了 32 位机器的速度，64 位只能在一个提取周期内完成操作。因此，很明显，对于较小的数据，如果我的处理器以相同的速度运行，也没有什么区别。编译器旨在为目标机器架构生成最高效的代码。

**注意:**有趣的是，我们不需要任何“长”数据类型，因为它们的替换(int，long long)已经可以从 [C99](https://en.wikipedia.org/wiki/C99) 标准获得。

在下面的程序中，定义了所有可能的长数据类型变量，并使用 [sizeof()](https://www.geeksforgeeks.org/sizeof-operator-c/) 运算符计算和打印它们的大小。

下面是查找长关键字演示工作的 C 程序:

```cpp
// C program to demonstrate the working
// of long keyword

#include <stdio.h>

int main()
{

    long longType;
    int integerType;
    long int longIntegerType;
    long long int longLongIntegerType;
    float floatType;
    double doubleType;
    long double longDoubleType;

    // Calculate and Print the size of all variables
    printf("Size of longType is: %ld\n",
           sizeof(longType));
    printf("Size of integerType is: %ld\n",
           sizeof(integerType));
    printf("Size of longIntegerType is: %ld\n",
           sizeof(longIntegerType));
    printf("Size of longLongIntegerType is: %ld\n",
           sizeof(longLongIntegerType));
    printf("Size of floatType is: %ld\n",
           sizeof(floatType));
    printf("Size of doubleType is: %ld\n",
           sizeof(doubleType));
    printf("Size of longDoubleType is: %ld\n",
           sizeof(longDoubleType));
    return 0;
}
```

**输出**:

```cpp
Size of longType is: 8
Size of integerType is: 4
Size of longIntegerType is: 8
Size of longLongIntegerType is: 8
Size of floatType is: 4
Size of doubleType is: 8
Size of longDoubleType is: 16

```