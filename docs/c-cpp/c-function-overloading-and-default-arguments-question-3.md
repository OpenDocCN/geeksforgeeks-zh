# C++ |函数重载和默认参数|问题 3

> 原文:[https://www . geesforgeks . org/c-function-overload-and-default-arguments-question-3/](https://www.geeksforgeeks.org/c-function-overloading-and-default-arguments-question-3/)

C++ 中不允许下列哪些重载函数？

1)仅在返回类型上不同的函数声明

```cpp
    int fun(int x, int y);
         void fun(int x, int y); 
```

2)返回类型中仅静态关键字不同的函数

```cpp
    int fun(int x, int y);
         static int fun(int x, int y); 
```

3)仅在指针*和数组[]上不同的参数声明

```cpp
int fun(int *ptr, int n);
int fun(int ptr[], int n); 
```

4)只有默认参数不同的两个参数声明

```cpp
int fun( int x, int y); 
int fun( int x, int y = 10); 
```

**(A)** 以上全部

**(B)** 除 2 外全部)
**(C)** 除 1 外全部)
**(D)** 除 2 和 4 外全部

**答案:****(A)**

**说明:**参见[c++ 中函数重载](https://www.geeksforgeeks.org/function-overloading-in-c/)

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)