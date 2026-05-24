# C |高级指针|问题 1

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-9/](https://www.geeksforgeeks.org/c-pointers-question-9/)

```cpp
void fun(int *p) 
{ 
  int q = 10; 
  p = &q; 
}     

int main() 
{ 
  int r = 20; 
  int *p = &r; 
  fun(p); 
  printf("%d", *p); 
  return 0; 
}
```

**(A)**10
**(B)**20
**(C)**编译器错误
**(D)** 运行时错误

**答案:****(B)**

**解释:** Inside fun()，q 是指针 p 的副本，所以如果我们把 q 改成指向别的东西，那么 p 仍然不受影响。如果我们想改变一个函数在另一个函数中的局部指针，那么我们必须将指针传递给指针。通过将指针传递给指针，我们可以将指针更改为指向其他东西。以下面的程序为例。

```cpp
void fun(int **pptr)
{
  static int q = 10;
  *pptr = &q;
}

int main()
{
  int r = 20;
  int *p = &r;
  fun(&p);
  printf("%d", *p);
  return 0;
}

```

在上面的例子中，fun()函数需要一个双指针(指向整数指针的指针)。Fun()修改地址 pptr 处的值。当我们将 p 的地址传给 fun()时，地址 pptr 处的值是指针 p。在 fun()中，pptr 处的值被更改为 q 的地址。因此，main()的指针 p 被更改为指向新的变量 q

另外，请注意，程序不会导致任何超出范围的问题，因为 q 是一个[静态](http://www.itee.uq.edu.au/~comp2303/Leslie_C_ref/C/CONCEPT/storage_class.html#static)变量。即使在函数返回之后，静态变量仍然存在于内存中。对于一个[自动](http://www.itee.uq.edu.au/~comp2303/Leslie_C_ref/C/CONCEPT/storage_class.html#auto)变量，我们可能会看到一些意想不到的输出，因为函数返回后，自动变量可能不存在于内存中。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)