# c++ 中的统一初始化

> 原文:[https://www.geeksforgeeks.org/uniform-initialization-in-c/](https://www.geeksforgeeks.org/uniform-initialization-in-c/)

统一初始化是 C++ 11 中的一个特性，它允许使用一致的语法来初始化从基元类型到聚合的变量和对象。换句话说，它引入了使用大括号({})括起初始值设定项值的大括号初始化。语法如下:

```cpp
type var_name{arg1, arg2, ....arg n}
```

以下是初始化不同类型的不同方法的一些示例:

```cpp
// uninitialized built-in type
int i;    

// initialized built-in type
int j=10; 

// initialized built-in type
int k(10);

// Aggregate initialization
int a[]={1, 2, 3, 4} 

// default constructor
X x1; 

// Parameterized constructor
X x2(1); 

// Parameterized constructor with single argument
X x3=3; 

// copy-constructor
X x4=x3; 
```

如果使用大括号初始化，上述代码可以重写为:

```cpp
int i{};     // initialized built-in type, equals to int i{0};

int j{10}; // initialized built-in type

int a[]{1, 2, 3, 4} // Aggregate initialization

X x1{}; // default constructor

X x2{1}; // Parameterized constructor;

X x4{x3}; // copy-constructor
```

**统一初始化的应用**

**动态分配阵列的初始化**:

## C++

```cpp
// C++ program to demonstrate initialization
// of dynamic array in C++ using uniform initialization
#include <bits/stdc++.h>
using namespace std;
int main()
{
    // declaring a dynamic array
    // and initializing using braces
    int* pi = new int[5]{ 1, 2, 3, 4, 5 };

    // printing the contents of the array
    for (int i = 0; i < 5; i++)
        cout << *(pi + i) << " ";
}
```

**Output**

```cpp
1 2 3 4 5 
```

**类的数组数据成员的初始化**:

## C++

```cpp
// C++ program to initialize
//  an array data member of a class
// with uniform initialization
#include <iostream>
using namespace std;

class A
{
    int arr[3];

public:
    // initializing array using
    // uniform initialization
    A(int x, int y, int z)
        : arr{ x, y, z } {};

    void show()
    {
        // printing the contents of the array
        for (int i = 0; i < 3; i++)
            cout << *(arr + i) <<" ";
    }
};

// Driver Code
int main()
{
    // New object created and the numbers
    // to initialize the array with, are passed
    // into it as arguments
    A a(1, 2, 3);
    a.show();
    return 0;
}
```

**Output**

```cpp
1 2 3 
```

**隐式初始化对象返回**:

## C++

```cpp
// C++ program to implicitly
// initialize an object to return
#include <iostream>
using namespace std;

// declaring a class 'A'
class A {
    // a and b are data members
    int a;
    int b;

    // constructor
public:
    A(int x, int y)
        : a(x)
        , b(y)
    {
    }
    void show() { cout << a << " " << b; }
};

A f(int a, int b)
{
    // The compiler automatically
    // deduces that the constructor
    // of the class A needs to be called
    // and the function parameters of f are
    // needed to be passed here
    return { a, b };
}

// Driver Code
int main()
{
    A x = f(1, 2);
    x.show();
    return 0;
}
```

**Output**

```cpp
1 2
```

**隐式初始化功能参数**

## C++

```cpp
// C++ program to demonstrate how to
// initialize a function parameter
// using Uniform Initialization

#include <iostream>
using namespace std;

// declaring a class 'A'
class A {

    // a and b are data members
    int a;
    int b;

public:
    A(int x, int y)
        : a(x)
        , b(y)
    {
    }
    void show() { cout << a << " " << b; }
};

void f(A x) { x.show(); }

// Driver Code
int main()
{

    // calling function and initializing it's argument
    // using brace initialization
    f({ 1, 2 });
    return 0;
}
```

**Output**

```cpp
1 2
```