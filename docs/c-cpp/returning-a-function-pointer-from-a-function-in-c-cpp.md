# 从 C/C++ 中的函数返回函数指针

> 原文:[https://www . geesforgeks . org/returning-a-function-pointer-from-in-c-CPP/](https://www.geeksforgeeks.org/returning-a-function-pointer-from-a-function-in-c-cpp/)

在 C/ C++ 中，像[普通数据指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/) (int *，char *，等)一样，可以有指向函数的指针。程序中创建的每个函数都在内存中获得一个地址，因为[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)可以在 [C](https://www.geeksforgeeks.org/c-programming-language/) / [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中使用，所以也可以创建一个指向函数的指针。

**语法:**

> **返回类型(* function _ pointer _ name)(argument _ type _ 1，argument_type_2，…，argument _ type _ n)=&function _ name；**
> 
> 运筹学
> 
> **返回类型(* function _ pointer _ name)(argument _ type _ 1，argument_type_2，…，argument _ type _ n)= function _ name；**

**注意:**函数指针的参数类型和返回类型应与程序中存在的实际函数相匹配。

**程序 1:**

## C

```cpp
// C program for the above approach
#include <stdio.h>

// Function to add the value 10 to
// the variable a
void demo(int* a) { *a += 10; }

// Driver Code
int main()
{
    int num = 20;

    // ptr contains address of demo
    // function or void
    void (*ptr)(int*) = &demo;

    // or (*ptr)(&num);
    ptr(&num);

    printf("%d", num);

    return 0;
}
```

## C++

```cpp
// C++ program for the above approach
#include <iostream>
using namespace std;

void demo(int& a)
{
    a += 10;
}

// Driver Code
int main()
{
    int num = 20;

    // Now ptr contains address of demo
    // function or void
    void (*ptr)(int*) = &demo;

    // or (*ptr)(num);
    ptr(num);

    cout << num << endl;

    return 0;
}
```

**Output**

```cpp
30
```

**从函数返回函数指针:**要从函数返回函数指针，函数的返回类型应该是指向另一个函数的指针。但是编译器不接受这样的函数返回类型，所以我们需要定义一个表示特定函数指针的类型。

**语法:**

> **typedef 返回类型(* function _ pointer _ name)(argument _ type _ 1，argument_type_2，…，argument _ type _ n)；**
> 
> 这将创建一个表示特定函数指针的类型。

**程序 2:**

## C

```cpp
// C program for the above approach
#include <stdio.h>
typedef int (*ptr)(int*);
typedef ptr (*pm)();

int fun1(int* y)
{
    printf("geeks!!\n");
    return *y + 10;
}

// Function that return type ptr
ptr fun()
{
    printf("Hello ");

    // or return fun1;
    /* or
     int(*pt)(int*)=fun1;
     return pt
  */
    return &fun1;
}

// Driver Code
int main()
{
    int a = 10;

    pm u = fun;

    printf("%d", (*u())(&a));

    return 0;
}
```

## C++

```cpp
// C++ program for the above approach
#include <iostream>
using namespace std;
typedef int (*ptr)(int*);
typedef ptr (*pm)();

int fun1(int* y)
{
    cout << "geeks!!" << endl;
    return *y + 10;
}

// Function that returns the type ptr
ptr fun()
{
    cout << "Hello ";
    return &fun1;
}

// Driver Code
int main()
{
    int a = 10;
    pm u = fun;
    cout << (*u())(&a) << endl;

    return 0;
}
```

**Output**

```cpp
Hello geeks!!
20
```

声明一个数组，该数组有两个指向其元素的函数指针，这些函数指针又返回指向其他函数的其他函数指针。在上述程序中，驱动程序代码 main()函数的逻辑可以更改为:

**程序 3:**

## C

```cpp
// C program for the above approach
#include <stdio.h>

// This defines a type for
// function prototypes
typedef int (*ptr)(int*);
typedef ptr (*pm)();

int fun1(int* y)
{
    printf("geeks!!\n");
    return *y + 10;
}

// fun() is a function with
// return type ptr
ptr fun()
{
    printf("Hello ");

    // or return fun1;
    /* or
     int(*pt)(int*)=fun1;
     return pt
  */
    return &fun1;
}

// Driver code
int main()
{
    int a = 10;
    pm u = fun;

    /*
    Above line assigns 'u' which is
    of type 'pm' to an array of size
    1 which has function pointers as
    its elements and these function
    pointers in turn return other
    function pointer which points to
    other functions.

    Now this 'p' array contains a function
    pointer 'u' which points to fun() and
    this fun() returns another function
    pointer which points to fun1().
  */
    int (*(*p[1])())(int*) = { u };

    printf("%d", (*p[0]())(&a));
}
```

## C++

```cpp
// C++ program for the above approach
#include <iostream>
using namespace std;

// This defines a type for
// function prototypes
typedef void (*ptr)(int&);
typedef ptr (*pm)();

void fun1(int& z)
{
    printf("geeks!!\n");
    cout << z + 10 << endl;
}

// Function that returns type ptr
ptr fun()
{
    printf("Hello ");

    // or return fun1;
    /* or
     int(*pt)(int*)=fun1;
     return pt
  */
    return &fun1;
}

// Driver Code
int main()
{
    int a = 10;
    pm u = fun;

    /*
    Above line assigns 'u' which is
    of type 'pm' to an array of size
    1 which has function pointers as its
    elements and these function pointers
    in turn return other function pointer
    which points to other functions.

    Now this 'p' array contains a function
    pointer 'u' which points to fun() and
    this fun() returns another function
    pointer which points to fun1() and
    this fun1() returns void.
  */
    void (*(*p[1])())(int&) = { u };

    (*p[0]())(a);
}
```

**Output**

```cpp
Hello geeks!!
20
```