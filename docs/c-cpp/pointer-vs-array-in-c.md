# 指针对 C 中数组

> 原文:[https://www.geeksforgeeks.org/pointer-vs-array-in-c/](https://www.geeksforgeeks.org/pointer-vs-array-in-c/)

大多数情况下，指针和数组访问可以被视为行为相同，主要的例外是:

1)sizeof 运算符
o sizeof(数组)返回数组中所有元素使用的内存量
o sizeof(指针)只返回指针变量本身使用的内存量

2)数组的&运算符
是&数组【0】的别名，返回数组
中第一个元素的地址&指针返回指针的地址

3)字符数组的字符串文字初始化
o char array[] = "abc "将数组中的前四个元素设置为' a '，' b '，' c '，而' \0'
o char *pointer = "abc "将指针设置为" abc "字符串的地址(该地址可能存储在只读存储器中，因此不可更改)

4)指针变量可以赋值，而数组变量不能。

```cpp
int a[10];
int *p; 
p=a; /*legal*/
a=p; /*illegal*/ 
```

5)允许对指针变量进行算术运算。

```cpp
p++ ; /*Legal*/
a++ ; /*illegal*/ 
```

**请参考**[**C 中指针和数组的区别？**](https://www.geeksforgeeks.org/difference-pointer-array-c/) **了解更多详情。**

参考文献:[http://icecube.wisc.edu/~dglo/c_class/array_ptr.html](http://icecube.wisc.edu/~dglo/c_class/array_ptr.html)T2】