# C语言循环与控制结构

## 问题13

> 原文：[https://www.geeksforgeeks.org/c-loops-control-structure-question-13/](https://www.geeksforgeeks.org/c-loops-control-structure-question-13/)

下面的C程序段会输出什么？(GATE CS 2012)

```cpp
char inchar = 'A';
switch (inchar)
{
case 'A' :
    printf ("choice A \n") ;
case 'B' :
    printf ("choice B ") ;
case 'C' :
case 'D' :
case 'E' :
default:
    printf ("No Choice") ;
}
```

**(A)** 无选择
**(B)** 选择 A
**(C)** 选择 A
选择 B 无选择
**(D)** 程序不给出输出，因为它是错误的

**回答：****(C)**

**解释：**在情况`'A'`下没有`break`语句。如果一个`case`被执行，并且它不包含`break`，那么所有后续的`case`都被执行，直到找到`break`语句。这就是为什么`switch`内的所有东西都被打印出来。

尝试以下程序作为练习。

```cpp
int main()
{
    char inchar = 'A';
    switch (inchar)
    {
    case 'A' :
        printf ("choice A \n") ;
    case 'B' :
    {
        printf ("choice B") ;
        break;
    }
    case 'C' :
    case 'D' :
    case 'E' :
    default:
        printf ("No Choice") ;
    }
}
```