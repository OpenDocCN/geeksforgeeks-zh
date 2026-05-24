# 指针与C中的数组

> 原文：[https://www.geeksforgeeks.org/pointer-vs-array-in-c/](https://www.geeksforgeeks.org/pointer-vs-array-in-c/)

大多数情况下，指针和数组访问可以被视为行为相同，主要的例外是：

1.  `sizeof` 运算符
    *   `sizeof(数组)` 返回数组中所有元素使用的内存量。
    *   `sizeof(指针)` 只返回指针变量本身使用的内存量。

2.  数组的 `&` 运算符
    *   `&数组` 是 `&数组[0]` 的别名，返回数组中第一个元素的地址。
    *   `&指针` 返回指针的地址。

3.  字符数组的字符串文字初始化
    *   `char array[] = "abc"` 将数组中的前四个元素设置为 `'a'`，`'b'`，`'c'` 和 `'\0'`。
    *   `char *pointer = "abc"` 将指针设置为字符串 `"abc"` 的地址（该地址可能存储在只读存储器中，因此不可更改）。

4.  指针变量可以赋值，而数组变量不能。

```cpp
int a[10];
int *p;
p = a; /* 合法 */
a = p; /* 非法 */
```

5.  允许对指针变量进行算术运算。

```cpp
p++; /* 合法 */
a++; /* 非法 */
```

请参考 [C中指针和数组的区别？](https://www.geeksforgeeks.org/difference-pointer-array-c/) 了解更多详情。

参考文献：[http://icecube.wisc.edu/~dglo/c_class/array_ptr.html](http://icecube.wisc.edu/~dglo/c_class/array_ptr.html)