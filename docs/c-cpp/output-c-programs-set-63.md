# C 程序输出|第 63 集

> 原文:[https://www.geeksforgeeks.org/output-c-programs-set-63/](https://www.geeksforgeeks.org/output-c-programs-set-63/)

**前提条件** : [结构填充](https://www.geeksforgeeks.org/structure-member-alignment-padding-and-data-packing/)、[整数提升](https://www.geeksforgeeks.org/integer-promotions-in-c/)、[顺序点](https://www.geeksforgeeks.org/sequence-points-in-c-set-1/)。
Q1**。**考虑以下代码:

## C

```cpp
#include<stdio.h>
struct geeks{
  int i;
  char c;
} obj;

int main()
{
  printf("%ld", sizeof(obj));
}
```

**上述代码的输出会是什么？**
**a .**4
**b .**5
**c .**8
**d .**无法确定

```cpp
Output: Can't be determined
```

**解说:**
都是关于[结构填充](https://www.geeksforgeeks.org/structure-member-alignment-padding-and-data-packing/)的。c 编译器知道在 RAM 中存储未对齐的数据可能成本很高，所以它会根据需求填充数据。如果一个结构中有 5 个字节的数据，它可能会变成 8 或 16 或 6。或者它想要的任何东西。有一些扩展，比如 GCC 属性**对齐**和**打包**，允许对这个过程进行一些控制，但是它们不是标准的。c 本身没有定义填充属性。所以正确答案是‘无法确定’。
**Q2。**考虑以下代码:

## C

```cpp
#include<stdio.h>

int main(){

  char a = 0;
  short int b = 0;
  printf("%d", sizeof(b) == sizeof(a+b));
  return 0;
}
```

**上述代码的输出会是什么？**
**a .**0
**b .**1
**c .**2
**d .**无法确定

```cpp
Output: Can't be determined
```

**解说:**都是关于[整数晋级](https://www.geeksforgeeks.org/integer-promotions-in-c/)的。当对“char”、“short int”等数据类型执行计算时，它们会自动升级为“int”。但即便如此，表达式(sizeof(b) == sizeof(a+b))比较的是大小而不是类型，根据 C 标准，保证“short int”的大小不能大于“int”的大小。因此，我们不能保证“sizeof(a+b)”将返回什么，因此正确答案是“无法确定”。
**Q3。**考虑以下代码:

## C

```cpp
#include<stdio.h>

int main()
{
  char a = ' ' * 13;
  printf("%d", a);
  return 0;
}
```

**上述代码的输出会是什么？**
**a .**416
**b .**160
**c .**-96
**d .**无法确定

```cpp
Output: Can't be determined
```

**说明:**
空格字符(')的 ASCII 值为 32，首先表达式 **(' ' * 13)** 不会出现整数溢出(因为整数提升)，因此行为未定义。其次，“char type”(有符号或无符号)不是由标准定义的，因此它将是特定于实现的。
但更重要的是，字符类型本身的大小也不是以位来指定的。有 6 位的平台([三位](https://en.wikipedia.org/wiki/Digraphs_and_trigraphs#C))，也有 5 种整数类型都是 32 位的平台。没有指定所有这些细节，对结果的每一个猜测都是无效的，所以答案是:“无法确定”。
**Q4。**考虑以下代码:

## C

```cpp
#include<stdio.h>

int main()
{
  int i = 16;
  printf("%d", (((i >= i) << i) >> i) <= i);
  return 0;
}
```

**上述代码的输出会是什么？**
**a .**0
**b .**1
**c .**16
**d .**无法确定

```cpp
Output: Can't be determined
```

**说明:**
上述表达式的输出是依赖于编译器的，因为 C 标准中没有直接规定‘int’的大小。它很容易是 16 位，那么比较后的第一个操作((i > = i) < < i)将导致过度移位，这是明显的未定义行为。这不是 C 的错，在某些平台上它甚至在汇编中是未定义的，所以编译器根本无法给出关于上述表达式的有效保证。因此，答案将是“无法确定”。
T4【Q5。考虑以下代码:

## C

```cpp
#include<stdio.h>

int main()
{
  int i = 0;
  int ans = i++ + ++ i;
  printf("%d ", ans);
  return 0;
}
```

**上述代码的输出会是什么？**T2**a .**1
T6 b .2
T9】c .3
T12】d .无法确定

```cpp
Output: Can't be determined
```

**解释:**
在 C 语言中，表达式“ **i++ + ++ i** 没有任何意义，因为它违反了没有[序列点](https://www.geeksforgeeks.org/sequence-points-in-c-set-1/)同一个变量不能被改变多次的规则。*序列点基本上是代码中编译器保证已经完成所有评估的点。例如，语句末尾的分号是序列点*。
在这个表达式中，变量‘I’值在没有序列点的情况下改变了两次。因此，编译器可以做它想做的任何事情，并且会导致未定义的行为。因此，答案将是“无法确定”。
**参考文献**:[https://hackernoon.com/so-you-think-you-know-c-8d4e2cd6f6a6](https://hackernoon.com/so-you-think-you-know-c-8d4e2cd6f6a6)