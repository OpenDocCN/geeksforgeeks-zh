# 什么是野指针？如何才能避免？

> 原文:[https://www . geesforgeks . org/什么是野生指针-我们如何避免/](https://www.geeksforgeeks.org/what-are-wild-pointers-how-can-we-avoid/)

未初始化的指针被称为野指针，因为它们指向一些任意的内存位置，并可能导致程序崩溃或行为不良。

```cpp
int main()
{
  int *p;  /* wild pointer */
   /* Some unknown memory location is being corrupted. 
   This should never be done. */ 
  *p = 12; 
}
```

请注意，如果指针 p 指向一个已知变量，那么它就不是一个野生指针。在下面的程序中，p 是一个野生指针，直到它指向 a。

```cpp
int main()
{
  int  *p; /* wild pointer */
  int a = 10;
  p = &a;  /* p is not a wild pointer now*/
  *p = 12; /* This is fine. Value of a is changed */ 
}
```

如果我们想要指向一个值(或一组值)的指针，而没有该值的变量，我们应该显式地分配内存，并将该值放入已分配的内存中。

```cpp
int main()
{
   int *p = (int *)malloc(sizeof(int));
  *p = 12; /* This is fine (assuming malloc doesn't return NULL) */ 
}
```