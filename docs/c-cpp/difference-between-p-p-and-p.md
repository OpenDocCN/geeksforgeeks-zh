# ++ * p、*p++ 和* +++ p 的区别

> 原文:[https://www.geeksforgeeks.org/difference-between-p-p-and-p/](https://www.geeksforgeeks.org/difference-between-p-p-and-p/)

预测以下 C 程序的输出。

## C

```cpp
// PROGRAM 1
#include <stdio.h>
int main(void)
{
    int arr[] = {10, 20};
    int *p = arr;
    ++*p;
    printf("arr[0] = %d, arr[1] = %d, *p = %d",
                          arr[0], arr[1], *p);
    return 0;
}
```

## C

```cpp
// PROGRAM 2
#include <stdio.h>
int main(void)
{
    int arr[] = {10, 20};
    int *p = arr;
    *p++ ;
    printf("arr[0] = %d, arr[1] = %d, *p = %d",
                          arr[0], arr[1], *p);
    return 0;
}
```

## C

```cpp
// PROGRAM 3
#include <stdio.h>
int main(void)
{
    int arr[] = {10, 20};
    int *p = arr;
    *++ p;
    printf("arr[0] = %d, arr[1] = %d, *p = %d",
                          arr[0], arr[1], *p);
    return 0;
}
```

以上程序以及所有这类程序的输出，只要记住以下关于后缀++、前缀++、*(取消引用)运算符的简单规则
**1)** 前缀++、*的优先级相同，就可以很容易猜到。两者的关联性是从右向左的。
**2)** 后缀++ 的优先级高于*和前缀++。后缀++ 的结合性是从左到右的。
(参考:[优先表](https://www.geeksforgeeks.org/operators-c-c/) )
表达式**+* p**有两个优先级相同的运算符，所以编译器会寻找结合性。运算符的关联性是从右向左的。因此该表达式被视为 ***++(*p)*** 。因此第一个程序的输出是“ *arr[0] = 11，arr[1] = 20，*p = 11* ”。
表达式 ***p++** 被视为 ****(p++)*** ，因为后缀++ 的优先级高于*。因此第二个程序的输出是“ *arr[0] = 10，arr[1] = 20，*p = 20* ”。
表达式 ***++ p** 有两个优先级相同的运算符，所以编译器会寻找关联性。运算符的关联性是从右向左的。因此该表达式被视为 ****(++ p)*** 。因此第三个程序的输出是“ *arr[0] = 10，arr[1] = 20，*p = 20* ”。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。