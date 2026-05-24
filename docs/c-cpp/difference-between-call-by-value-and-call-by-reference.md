# 按值调用和按引用调用的区别

> 原文:[https://www . geesforgeks . org/按值调用和按引用调用的区别/](https://www.geeksforgeeks.org/difference-between-call-by-value-and-call-by-reference/)

函数有两种调用方式:**按值调用**或**按引用调用**。这两种方式通常由作为参数传递给它们的值的类型来区分。

传递给函数的参数称为*实际参数*，而函数接收的参数称为*形式参数*。

**按值调用**:在这个参数传递方法中，实际参数的值被复制到函数的形式参数中，两种类型的参数存储在不同的内存位置。因此，函数内部所做的任何更改都不会反映在调用者的实际参数中。

**引用调用**:实际参数和形式参数都引用相同的位置，所以函数内部所做的任何更改实际上都反映在调用方的实际参数中。T39】

| call by value | Call by reference |
| --- | --- |
| When calling a function, we pass the value of a variable to it. This kind of function is called "calling by value". | When calling a function, instead of passing the value of a variable, we pass the address of the variable (the location of the variable) to a function called "Call by Reference". |
| This method copies the value of each variable in the calling function to the pseudo variable corresponding to the called function. | This method copies the address of the actual variable in the calling function to the dummy variable of the called function. |
| With this method, changes made to virtual variables in the called function will not affect the values of actual variables in the calling function. | In this way, using addresses, we can access actual variables, so we can manipulate them. |
| 

```cpp
// C program to illustrate
// call by value

#include // Function Prototype
void swapx(int x, int y);

// Main function
int main()
{
    int a = 10, b = 20;

    // Pass by Values
    swapx(a, b);

    printf("a=%d b=%d\n", a, b);

    return 0;
}

// Swap functions that swaps
// two values
void swapx(int x, int y)
{
    int t;

    t = x;
    x = y;
    y = t;

    printf("x=%d y=%d\n", x, y);
}

**Output:**
x=20 y=10
a=10 b=20 
```

 | 

```cpp
// C program to illustrate
// Call by Reference

#include // Function Prototype
void swapx(int*, int*);

// Main function
int main()
{
    int a = 10, b = 20;

    // Pass reference
    swapx(&a, &b);

    printf("a=%d b=%d\n", a, b);

    return 0;
}

// Function to swap two variables
// by references
void swapx(int* x, int* y)
{
    int t;

    t = *x;
    *x = *y;
    *y = t;

    printf("x=%d y=%d\n", *x, *y);
}

**Output:**
x=20 y=10
a=20 b=10 
```

 |