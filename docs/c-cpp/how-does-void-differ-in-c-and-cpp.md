# “void *”在 C 和 C++ 中有何区别？

> 原文:[https://www . geesforgeks . org/how-do-void-different-in-c-and-CPP/](https://www.geeksforgeeks.org/how-does-void-differ-in-c-and-cpp/)

C 允许将 void*指针赋给任何没有强制转换的指针类型，而在 C++ 中，则不允许。我们必须在 C++ 中显式地类型转换 void*指针

例如，以下内容在 C 中有效，但在 C++ 中无效:

```cpp
void* ptr;
int *i = ptr; // Implicit conversion from void* to int*
```

同样，

```cpp
int *j = malloc(sizeof(int) * 5);  // Implicit conversion from void* to int* 
```

为了让上面的代码也用 C++ 编译，我们必须使用显式转换，如下所示，

```cpp
void* ptr;
int *i = (int *) ptr;
int *j = (int *) malloc(sizeof(int) * 5);
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。