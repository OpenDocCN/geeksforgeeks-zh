# std::bad_array_new_length 类在 C++ 中有示例

> 原文: [https://www.geeksforgeeks.org/stdbad_array_new_length-class-in-c-with-examples/](https://www.geeksforgeeks.org/stdbad_array_new_length-class-in-c-with-examples/)

标准 C++ 包含几个内置的异常类，`std::bad_array_new_length`就是其中之一。如果数组的大小小于零，并且数组的大小大于限制，则抛出异常。下面是相同的语法:

## 头文件:

```cpp
<new>
```

## 语法:

```cpp
class bad_array_new_length;
```

## 返回:

`std::bad_array_new_length`返回一个空终止字符，用于标识异常。

## 注意:

要使用 `std::bad_array_new_length`，应该设置合适的try-catch块。

以下是以更好的方式理解 `std::bad_array_new_length` 实现的程序:

### 程序 1:

```cpp
// C++ code for std::bad_array_new_length
#include <bits/stdc++.h>

using namespace std;

// main method
int main()
{
    int a = -1;
    int b = 1;
    int c = INT_MAX;

// try block
    try {
        new int[a];
        new int[b]{
            1,
            2,
            3,
        };
        new int[50000000];
    }

// catch block to handle the errors
    catch (const bad_array_new_length& gfg) {
        cout << gfg.what() << endl;
    }

    return 0;
}
```

### 输出:

```cpp
std::bad_array_new_length
```

### 程序二:

```cpp
// C++ code for std::bad_array_new_length
#include <bits/stdc++.h>

using namespace std;

// main method
int main()
{
    int a = -1;
    int b = 1;
    int c = INT_MAX;

// try block
    try {
        new int[a];
        new int[b]{
            11,
            25,
            56,
        };
        new int[1000000];
    }

// catch block to handle the errors
    catch (const bad_array_new_length& gfg) {
        cout << gfg.what() << endl;
    }
    return 0;
}
```

### 输出:

```cpp
std::bad_array_new_length
```

## 参考:

[http://www.cplusplus.com/reference/new/bad_array_new_length/](http://www.cplusplus.com/reference/new/bad_array_new_length/)