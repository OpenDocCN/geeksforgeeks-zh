# c++ 中的默认参数

> 原文:[https://www.geeksforgeeks.org/default-arguments-c/](https://www.geeksforgeeks.org/default-arguments-c/)

默认参数是在函数声明中提供的值，如果函数的调用方没有为参数提供默认值，则编译器会自动分配该值。如果传递了任何值，默认值将被覆盖。

**1)** 下面是一个简单的 C++ 例子，演示默认参数的使用。这里，我们不需要编写 3 个 sum 函数，只有一个函数使用第 3 个和第 4 个参数的默认值。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP Program to demonstrate Default Arguments
#include <iostream>
using namespace std;

// A function with default arguments,
// it can be called with
// 2 arguments or 3 arguments or 4 arguments.
int sum(int x, int y, int z = 0, int w = 0)
{
    return (x + y + z + w);
}

// Driver Code
int main()
{
    // Statement 1
    cout << sum(10, 15) << endl;

    // Statement 2
    cout << sum(10, 15, 25) << endl;

    // Statement 3
    cout << sum(10, 15, 25, 30) << endl;
    return 0;
}
```

**Output**

```cpp
25
50
80
```

**说明:**在语句 1 中，只传递了两个值，因此变量 z 和 w 取默认值为 0。在语句 2 中，传递了三个值，因此 z 的值被 25 覆盖。在语句 3 中，传递了四个值，因此 z 和 w 的值分别被 25 和 30 覆盖。

**2)** 当函数重载和默认值一起完成时。那么我们需要确保它不会模棱两可。
如果不明确，编译器会抛出一个错误。以下是上述程序的修改版本，

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP Program to demonstrate Function overloading in
// Default Arguments
#include <iostream>
using namespace std;

// A function with default arguments, it can be called with
// 2 arguments or 3 arguments or 4 arguments.
int sum(int x, int y, int z = 0, int w = 0)
{
    return (x + y + z + w);
}
int sum(int x, int y, float z = 0, float w = 0)
{
    return (x + y + z + w);
}
// Driver Code
int main()
{
    cout << sum(10, 15) << endl;
    cout << sum(10, 15, 25) << endl;
    cout << sum(10, 15, 25, 30) << endl;
    return 0;
}
```

**错误:**

```cpp
prog.cpp: In function 'int main()':
prog.cpp:17:20: error: call of overloaded 
'sum(int, int)' is ambiguous
  cout << sum(10, 15) << endl; 
                    ^
prog.cpp:6:5: note: candidate: 
int sum(int, int, int, int)
 int sum(int x, int y, int z=0, int w=0) 
     ^
prog.cpp:10:5: note: candidate: 
int sum(int, int, float, float)
 int sum(int x, int y, float z=0, float w=0) 
     ^
```

**要点:**

*   默认参数不同于常量参数，因为常量参数不能更改，而如果需要，默认参数可以被覆盖。
*   当调用函数为默认参数提供值时，默认参数将被覆盖。例如，调用函数 sum(10，15，25，30)会将 z 和 w 的值分别改写为 25 和 30。
*   在函数调用过程中，从调用函数到被调用函数的参数从左向右复制。因此，sum(10，15，25)会将 10，15 和 25 分配给 x，y 和 z。因此，默认值仅用于 w。
*   一旦默认值用于函数定义中的某个参数，该参数的所有后续参数都必须具有默认值。也可以说默认参数是从右向左分配的。例如，以下函数定义无效，因为默认变量 z 的后续参数不是默认值。

```cpp
// Invalid because z has default value, but w after it doesn't have a default value
int sum(int x, int y, int z = 0, int w).
```