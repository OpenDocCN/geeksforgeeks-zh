# C/c++ 中的多维指针算法

> 原文:[https://www . geesforgeks . org/多维-指针-算术-in-cc/](https://www.geeksforgeeks.org/multidimensional-pointer-arithmetic-in-cc/)

在 C/C++ 中，除了类型信息之外，数组和指针具有相似的语义。

举个例子，给定一个三维数组

```cpp
int buffer[5][7][6];
```

位置[2][1][2]处的元素可以作为“*缓冲区[2][1][2]* ”或 **( *(缓冲区+ 2) + 1) + 2)* 来访问。

遵守以下声明

```cpp
T *p; // p is a pointer to an object of type T
```

当指针 *p* 指向类型 T 的对象时，表达式 **p* 为类型 T。例如*缓冲区*为 5 个二维数组的数组类型。表达式**缓冲区*的类型是“数组的数组(即二维数组)”。

基于上述概念，逐步翻译表达式 **( *( *(缓冲区+ 2) + 1) + 2)* 会使其更加清晰。

1.  *Buffer* –An array of five two-dimensional arrays, that is, its type is "five two-dimensional arrays".
2.  *Buffer+2* –The displacement of the third element in five two-dimensional arrays.
3.  ** (buffer+2)* -dereference, that is, its type is now a two-dimensional array.
4.  ** (buffer+2)+1* -Access the displacement of the second element in 7 one-dimensional arrays.
5.  ** (* (buffer+2)+1)* -dereference (access). Now the expression " ** (* (buffer+2)+1)* " is an integer array.
6.  ** (* (buffer+2)+1)+2* -Get the displacement of the 3rd element in one-dimensional integer array.
7.  ** (* (* (buffer+2)+1)+2)* -access the element in the third position (the overall expression type is *int [now T33]).*

编译器计算一个“偏移量”来访问数组元素。“偏移量”是根据数组的维度计算的。在上述情况下，*偏移量= 2 *(T2)7 * 6)+1 *(T4)6)+2*。蓝色为尺寸，*注意偏移计算*不使用较高的尺寸。在编译期间，编译器知道数组的维数。使用偏移我们可以访问如下所示的元素，

```cpp
element_data = *( (int *)buffer + offset );
```

在编译时声明数组的维数并不总是可能的。有时我们需要将缓冲区解释为多维数组对象。例如，当我们在运行时处理其尺寸被确定的三维图像时，通常的数组下标规则不能被使用。这是由于在编译时缺少固定的维度。考虑下面的例子，

```cpp
int *base;
```

其中*基*是表示三维图像的指向大图像缓冲区 *l x b x h* ，其中 l、b 和 h 是变量。如果我们想在位置(2，3，4)访问一个元素，我们需要计算元素的偏移量为

*偏移量= 2 * (b x h) + 3 * (h) + 4* 以及位于*基地的元素+偏移量*。

进一步概括，给定大小为[ **l x b x h** ]维度的数组的起始地址(比如 *base* ，我们可以通过以下方式访问任意位置( **a，b，c** )的元素，

*数据= *(base+a *(T1)b x h)+b *(T3)h)+c)；* //注意，我们没有使用更高维度的 ***l*** 。

同样的概念可以应用于任何数量的维度。我们不需要更高维来计算多维数组中任何元素的偏移量。*就是我们把多维数组传递给函数*时省略高维的背后原因。只有当程序员迭代有限数量的高维元素时，才需要高维。

一个 C/C++ 难题，预测以下程序的输出

```cpp
int main()
{
    char arr[5][7][6];
    char (*p)[5][7][6] = &arr;

    /* Hint: &arr - is of type const pointer to an array of
       5 two dimensional arrays of size [7][6] */

    printf("%d\n", (&arr + 1) - &arr);
    printf("%d\n", (char *)(&arr + 1) - (char *)&arr);
    printf("%d\n", (unsigned)(arr + 1) - (unsigned)arr);
    printf("%d\n", (unsigned)(p + 1) - (unsigned)p);

    return 0;
}
```

**输出:**

**1**

**Two hundred and ten**

**forty-two**

**Two hundred and ten**

**感谢**学生**指出错误。**

**——**[文基](https://www.geeksforgeeks.org/?page_id=2)** 。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**