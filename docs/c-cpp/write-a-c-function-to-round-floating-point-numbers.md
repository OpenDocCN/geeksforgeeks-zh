# 写一个单行的 C 函数来舍入浮点数

> 原文:[https://www . geesforgeks . org/write-a-c-function-to-round-floating-point-numbers/](https://www.geeksforgeeks.org/write-a-c-function-to-round-floating-point-numbers/)

**算法:**轮数(num)
1。如果 num 为正，则添加 0.5。
2。否则减去 0.5。
3。类型将结果转换为 int 并返回。

**示例:**
num = 1.67，(int)num+0.5 =(int)2.17 = 2
num =-1.67，(int)num–0.5 =-(int)2.17 =-2
 **实现:**

```cpp
/* Program for rounding floating point numbers */
# include<stdio.h>

int roundNo(float num)
{
    return num < 0 ? num - 0.5 : num + 0.5;
}

int main()
{
    printf("%d", roundNo(-1.777));
    getchar();
    return 0;
}
```

输出:-2

**时间复杂度:**O(1)
T3】空间复杂度: O(1)

现在试着舍入给定的精度。也就是说，如果给定的精度是 2，那么函数应该为 1.63322 返回 1.63，为 1.6332 返回-1.63。