# 在 C++ 中传递对指针的引用

> 原文:[https://www . geesforgeks . org/passing-reference-to-a-pointer-in-c/](https://www.geeksforgeeks.org/passing-reference-to-a-pointer-in-c/)

**先决条件**:[c++ 中的指针与引用](https://www.geeksforgeeks.org/pointers-vs-references-cpp/)。

为了清楚地理解，让我们比较一下“指针对指针”和“引用对指针”在某些情况下的用法。

**注意:**C 和 C++ 都允许使用“指针对指针”，但我们只能在 C++ 中使用“引用对指针”。

**将指针传递给函数**

如果指针作为参数传递给函数并试图修改，那么对指针所做的更改不会反映到该函数之外。这是因为只有指针的副本被传递给函数。可以说“通过指针传递”就是[通过数值](https://www.geeksforgeeks.org/passing-by-pointer-vs-passing-by-reference-in-c/)传递指针。在大多数情况下，这不会带来问题。但是当您修改函数内部的指针时，问题就来了。您不是修改变量，而是只修改指针的副本，原始指针保持不变。

下面的程序说明了这一点:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>

using namespace std;

int global_Var = 42;

// function to change pointer value
void changePointerValue(int* pp)
{
    pp = &global_Var;
}

int main()
{
    int var = 23;
    int* ptr_to_var = &var;

    cout << "Passing Pointer to function:" << endl;

    cout << "Before :" << *ptr_to_var << endl; // display 23

    changePointerValue(ptr_to_var);

    cout << "After :" << *ptr_to_var << endl; // display 23

    return 0;
}
```

**Output:**

```cpp
Passing Pointer to function:
Before :23
After :23

```

**将“指针对指针”作为参数传递给功能**

上述问题可以通过将指针的地址传递给函数而不是实际函数的副本来解决。为此，函数参数应该接受“指针对指针”，如下图所示:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>

using namespace std;

int global_var = 42;

// function to change pointer to pointer value
void changePointerValue(int** ptr_ptr)
{
    *ptr_ptr = &global_var;
}

int main()
{
    int var = 23;
    int* pointer_to_var = &var;

    cout << "Passing a pointer to a pointer to function " << endl;

    cout << "Before :" << *pointer_to_var << endl; // display 23

    changePointerValue(&pointer_to_var);

    cout << "After :" << *pointer_to_var << endl; // display 42

    return 0;
}
```

**Output:**

```cpp
Passing a pointer to a pointer to function 
Before :23
After :42

```

**如何调用带有“引用指针”参数的函数？**

引用允许被调用的函数修改调用者函数的局部变量。例如，考虑以下示例程序，其中 fun()能够修改 main()的局部变量 x。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>

using namespace std;

void fun(int &x) { 
    x = 20; 
} 

int main() { 
    int x = 10; 
    fun(x); 
    cout<<"New value of x is "<<x; 
    return 0; 
}
```