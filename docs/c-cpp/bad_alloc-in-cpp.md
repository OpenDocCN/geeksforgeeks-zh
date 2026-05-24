# c++ 中的 bad _ alloc

> 原文:[https://www.geeksforgeeks.org/bad_alloc-in-cpp/](https://www.geeksforgeeks.org/bad_alloc-in-cpp/)

先决条件:[c++ 中的异常](https://www.geeksforgeeks.org/exception-handling-c/)

标准 C++ 包含几个内置的异常类。最常用的是 bad_alloc，当试图用 new 分配内存时，如果出现错误，就会引发该错误。

此类派生自异常。

要使用 bad_alloc，应该设置适当的尝试和捕获块。这里有一个简短的例子，展示了它是如何使用的:

## C++

```cpp
// CPP code for bad_alloc
#include <iostream>
#include <new>

// Driver code
int main () {
  try
  {
     int* gfg_array = new int[100000000];
  }
  catch (std::bad_alloc & ba)
  {
     std::cerr << "bad_alloc caught: " << ba.what();
  }
  return 0;
}
```

RunTime error :

```cpp
bad_alloc caught: std::bad_alloc

```