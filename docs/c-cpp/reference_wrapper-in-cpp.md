# c++ 中的 reference _ wrapper

> 原文:[https://www.geeksforgeeks.org/reference_wrapper-in-cpp/](https://www.geeksforgeeks.org/reference_wrapper-in-cpp/)

**std::reference_wrapper** 是一个类模板，它将引用包装在可复制构造和可复制分配的对象或对类型为 T 的函数的引用中。
实例 **std::reference_wrapper** 是对象(它们可以被复制或存储在容器中)，但它们可以隐式转换为**“T”&“**”，以便它们可以用作引用基础类型的函数的参数。

**语法:**

```cpp
template <class T> class reference_wrapper;
template parameter(T): type of the referred element and
                        this can be  either function or object.

```

示例:

```cpp
// C++ program to demonstrate the
// use of std::reference_wrapper
#include <iostream>    
#include <functional> 
using namespace std;

int main () 
{
    char a = 'g', b = 'e', c  = 'e', d = 'k', e = 's';

    // creating an array of character "references":
    reference_wrapper<char> ref[] = {a, b, c, d, e};

    for (char& s : ref)
          cout << s;

    return 0;
}
```

输出:

```cpp
geeks

```