# 字符串::C++ 中的 NPO，示例

> 原文: [https://www.geeksforgeeks.org/stringnpos-in-c-with-examples/](https://www.geeksforgeeks.org/stringnpos-in-c-with-examples/)

## 什么是 `string::npos`

*   对于类型为 `size_t` 的元素，它是一个具有最高可能值的常量静态成员。
*   实际意思是直到字符串结束。
*   它用作字符串成员函数中长度参数的值。
*   作为返回值，它通常用于指示没有匹配项。

## 语法

> `static const size_t npos = -1;`
> 其中，`npos` 是类型为 `size_t` 的元素的最大可能值的恒定静态值，用 -1 定义。

## 程序 1

下面是 C++ 程序来说明 `string::npos` 的用法：

### C++

```cpp
// C++ program to demonstrate the use
// of string::npos
#include <bits/stdc++.h>
using namespace std;

// Function that using string::npos
// to find the index of the occurrence
// of any string in the given string
void fun(string s1, string s2)
{
    // Find position of string s2
    int found = s1.find(s2);

    // Check if position is -1 or not
    if (found != string::npos) {

        cout << "first " << s2
             << " found at: "
             << (found) << endl;
    }

    else
        cout << s2 << " is not in"
             << "the string" << endl;
}

// Driver Code
int main()
{
    // Given strings
    string s1 = "geeksforgeeks";
    string s2 = "for";
    string s3 = "no";

    // Function Call
    fun(s1, s2);

    return 0;
}
```

**Output:**

```cpp
first for found at: 5
```

**说明:** 在上面的程序中 `string::npos` 常量的定义值为 -1，因为 `size_t` 是无符号整数类型，而 -1 是该类型最大的可能表示值。