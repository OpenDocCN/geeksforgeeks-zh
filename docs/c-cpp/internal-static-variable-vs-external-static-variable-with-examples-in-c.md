# 内部静态变量与外部静态变量，示例见 C

> 原文:[https://www . geesforgeks . org/internal-static-variable-vs-external-static-variable-with-examples-in-c/](https://www.geeksforgeeks.org/internal-static-variable-vs-external-static-variable-with-examples-in-c/)

[静态变量](https://www.geeksforgeeks.org/static-variables-in-c/)可以是内部的，也可以是外部的，具体取决于申报的地点。静态变量存储在初始化的数据段中。

**内部静态变量:**内部静态变量被定义为那些在函数内部声明的静态变量，并一直延伸到特定函数的末尾。

**语法:**

```cpp

main( ) 
{
  static datatype variable;
  // other statements
}

```

**示例:**

```cpp
// C program to demonstrate
// Internal Static Variables

#include <stdio.h>

int value();

int main()
{
    printf("%d", value());
    return 0;
}

int value()
{
    static int a = 5;
    return a;
}
```

**Output:**

```cpp
5

```

**外部静态变量:**外部静态变量是在函数外部声明的变量，为整个文件/程序全局设置。

**语法:**

```cpp

static datatype variable;

main()
{
  statements
}

function1()
{
  statements
}

```

**示例:**

```cpp
// C program to demonstrate
// External Static Variables

#include <stdio.h>

int add(int, int);

static int a = 5;

int main()
{
    int c;
    printf("%d", add(a, c));
}

int add(int c, int b)
{
    b = 5;
    c = a + b;
    return c;
}
```

**Output:**

```cpp
10

```

**内部静态变量和外部静态变量的区别:**

| 参数 | 内部静态变量 | 外部静态变量 |
| --- | --- | --- |
| 关键字 | “静态” | “静态” |
| 联系 | 内部静态变量没有链接。 | 外部静态变量有内部联系。 |
| 申报 | 内部静态变量在主函数中声明 | 外部静态变量在主函数之上声明。 |
| 比较 | 内部静态变量类似于自动(局部)变量。 | 外部静态变量类似于全局(外部)变量。 |
| 能见度 | 内部静态变量在特定函数中是活动的(可见性)。 | 外部静态变量在整个程序中是活动的(可见的)。 |
| 一生 | 内部静态变量在函数结束之前是活动的(生存期)。 | 外部静态变量在整个程序中是活动的(生存期)。 |
| 范围 | 内部静态变量具有块范围的持久存储(仅在特定的块或函数中工作)。 | 外部静态变量具有文件范围的永久存储(在整个程序中起作用)。 |