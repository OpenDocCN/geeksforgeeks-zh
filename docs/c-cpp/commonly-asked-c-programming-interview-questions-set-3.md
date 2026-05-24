# 常见 C 编程面试问题|第三集

> 原文:[https://www . geesforgeks . org/common-question-c-programming-interview-questions-set-3/](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-3/)

**问题 1 写下最小的可执行代码？**
俺们。main 是执行代码所必需的。代码是

## C

```cpp
void main()
{
}
```

**Output:** 

**问题 2 什么是进入控制和退出控制回路？**
俺们。c 只支持 2 个循环:

1.  **进入控制**:该循环分为两部分
    a .而循环
    b .为循环
2.  **退出控制:**在这个类别中，有一种循环被称为
    a. do while 循环。

**问题 3 为什么预处理器指令最后没有分号？**
俺们。**分号是编译器需要的，顾名思义 Preprocessors 就是在编译前处理我们源代码的程序。**因此不需要分号。
**问 4 包含带内角括号的头文件< >和双引号“”有什么区别？**
Ans。如果头文件包含在< >中，则编译器仅在内置包含路径中搜索特定头文件。如果头文件包含在" "，则编译器首先在当前工作目录中搜索特定头文件，如果没有找到，则在内置的包含路径中搜索。
**问 5 近、远、巨指针有什么区别？**
Ans。这些都是 MS DOS 时代 16 位英特尔架构中使用的一些老概念，已经没什么用了。
**近指针**用于存储 16 位机器当前段内的 16 位地址。限制是我们一次只能访问 64kb 的数据。
A **远指针**通常为 32 位，可以访问当前段外的内存。为此，编译器分配一个段寄存器来存储段地址，然后分配另一个寄存器来存储当前段内的偏移量。
和远指针一样，**巨大指针**也是典型的 32 位，可以访问外部段。在远指针的情况下，段是固定的。在远指针中，线段部分不能修改，但在巨指针中可以修改

<figure class="table">

| 近指针 | 远指针 |
| --- | --- |
| 它的大小是 2 字节 | 它的大小是 4 字节 |
| 他们的地址在 0-65535 之间(即在用户区) | 他们的地址超过 65535(即超出用户区域) |
| 例如:
简单的指针，我们通常在 C 和 C++ 中学习 | 在运行程序的设备中使用的指针，即通过该指针攻击其他计算机。 |

</figure>

**问题 6 为什么“类型降级”不存在，而“类型提升”不存在？此外，它将消耗更少的空间资源比做它从类型推广。？**
俺们。我们举个例子来理解一下。
假设
**双 a = 1.5int b=10，我们要计算 a+b**
通过类型降级，float 类型 a 将转换为 int。因此 a=1，a+b=1+10=11，但我们知道正确答案是 11.5，只有通过类型提升才能得到。所以结论是通过类型降级我们不会得到正确的答案。
**问 7 什么是堆栈和堆区？**

1.  **堆区:**用于动态分配的对象(使用 malloc()和 calloc())。
2.  **栈区:**用于存储一个方法的局部变量和自变量。这仅会保留在内存中，直到该特定方法终止。

详见[堆栈 vs 堆内存](https://www.geeksforgeeks.org/stack-vs-heap-memory-allocation/)。
**问 8 C 中的#include 和 Java 中的 import 的区别？**
Ans。

<figure class="table">

| #包括 | leading-in |
| --- | --- |
| # include is a statement, not a keyword.
 | Import is the key word. |
| Processed by preprocessor software. | Handled by the compiler. |
| It increases the size of the code. | It does not increase the size of the code. Here, even if we write
to import java.lang. *;
It does not attach all classes. Instead, it will allow access to java.lang's classes. |

</figure>

**q . 9++ * p、*p++ 和* +++ p 的区别？**
**1)** 前缀++ 和*的优先级相同。两者的关联性是从右向左的。
**2)** 后缀++ 的优先级高于*和前缀++。后缀++ 的结合性是从左到右的。
(参考:[优先级表](https://www.geeksforgeeks.org/operators-c-c/) )
表达式 **++*p** 有两个优先级相同的运算符，所以编译器会寻找关联性。运算符的关联性是从右向左的。因此该表达式被视为 ***++(*p)*** 。因此第一个程序的输出是“ *arr[0] = 10，arr[1] = 20，*p = 11* ”。
表达式 ***p++** 被视为 ****(p++)*** ，因为后缀++ 的优先级高于*。因此第二个程序的输出是“ *arr[0] = 10，arr[1] = 20，*p = 20* ”。
表达式 ***++ p** 有两个优先级相同的运算符，所以编译器会寻找关联性。运算符的关联性是从右向左的。因此该表达式被视为 ****(++ p)*** 。因此第三个程序的输出为“ *arr[0] = 10，arr[1] = 20，* p = 20*”
详情请参考++*p、*p++ 与* +++ p 的[区别。
**问题 10 用例子解释深抄和浅抄？**
在下面的 C 程序中，struct 变量 st1 包含指向动态分配内存的指针。当我们将 st1 分配给 st2 时，st2 的 str 指针也开始指向相同的存储位置。这种复制称为**浅复制**。](https://www.geeksforgeeks.org/difference-between-p-p-and-p/)

## C

```cpp
// C program to demonstrate shallow copy
# include <stdio.h>
# include <string.h>
# include <stdlib.h>

struct test
{
  char *str;
};

int main()
{
  struct test st1, st2;
  st1.str = (char *)malloc(sizeof(char) * 20);

  strcpy(st1.str, "GeeksforGeeks");

  st2 = st1;
  st1.str[0] = 'X';
  st1.str[1] = 'Y';

  /* Since copy was shallow, both strings are same */
  printf("st1's str = %s\n", st1.str);
  printf("st2's str = %s\n", st2.str);

  return 0;
}
```

**Output:** 

```cpp
st1's str = XYeksforGeeks
st2's str = XYeksforGeeks
```

为了进行**深度复制**，我们为动态分配的成员分配新的内存，并显式复制它们。

## C

```cpp
// C program to demonstrate deep copy
# include <stdio.h>
# include <string.h>
# include <stdlib.h>

struct test
{
  char *str;
};

int main()
{
  struct test st1, st2;
  st1.str = (char *)malloc(sizeof(char) * 20);

  strcpy(st1.str, "GeeksforGeeks");

  st2 = st1;

  // We add extra statements to do deep copy
  st2.str = (char *)malloc(sizeof(char) * 20);
  strcpy(st2.str, st1.str);

  st1.str[0] = 'X';
  st1.str[1] = 'Y';

  /* Since copy was deep, both strings are different */
  printf("st1's str = %s\n", st1.str);
  printf("st2's str = %s\n", st2.str);

  return 0;
}
```

**Output:** 

```cpp
st1's str = XYeksforGeeks
st2's str = GeeksforGeeks
```

### 相关文章:

1.[https://www . geeksforgeeks . org/common-question-c-programming-interview-questions-set-1/](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-1/)
2。[https://www . geeksforgeeks . org/common-question-c-programming-interview-questions-set-2/](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-2/)