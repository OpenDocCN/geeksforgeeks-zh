# 全局变量会有危险吗？

> 原文:[https://www . geesforgeks . org/can-global-variables-be-dangerous/](https://www.geeksforgeeks.org/can-global-variables-be-dangerous/)

在一个小代码中，我们可以跟踪全局变量的值。但是如果代码变大，它们会使代码不容易理解(因此不容易维护)。很难跟踪哪个函数修改了值以及如何修改的。

## c++

```cpp
// A C++ program to demonstrate that a
// global variables make long code less
// maintainable.

int c = 1;

int fun1()
{
   // 100 lines of code that
   // may modify c and also
   // call fun2()
}

void fun2()
{
   // 100 lines of code that
   // may modify c and also
   // call fun1()
}

void main()
{
    // 1000 lines of code

    c = 0;

    // 1000 lines of code

    // At this point, it becomes difficult
    // to trace value of c
    if (c == 1)
        cout << "c is 1" << endl
    else
        cout << "c is not 1 << endl
}
```

*   In the above code, we noticed that the biggest problem of global variables is **debugging** . This means that if we try to find out the variation of the variable **c** between thousands of lines of code, it is very difficult.
*   In a multithreaded environment, a global variable may change more than once (in a different execution order), resulting in more problems.
*   Global variables are generally used for constants. They are not recommended for outliers.