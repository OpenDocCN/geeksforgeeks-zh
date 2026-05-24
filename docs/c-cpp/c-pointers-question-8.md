# C |指针基础|问题 8

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-8/](https://www.geeksforgeeks.org/c-pointers-question-8/)

```cpp
int main()
{
 char *ptr = "GeeksQuiz";
 printf("%c\n", *&*&*ptr);
 return 0;
}
```

**(A)** 编译器错误
**(B)** 垃圾值
**(C)** 运行时错误
**(D)**G

**答案:****(D)**

**解释:**运算符*用于解引用，运算符&用于获取地址。这些运算符在相继使用时会相互抵消。我们可以多次交替使用它们。在上面的代码中，ptr 是指向字符串 g 的第一个字符的指针，*ptr 给出我们 g，& *ptr 给出 g 的地址，* & *ptr 再次给出 g，& * & *ptr 给出 g 的地址，最后* & * & *ptr 给出‘g’

现在试试下面

```cpp
int main()
{
 char *ptr = "GeeksQuiz";
 printf("%s\n", *&*&ptr);
 return 0;
}
```

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/pointers-gq/)