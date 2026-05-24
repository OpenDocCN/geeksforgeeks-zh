# c++ 中的 std::basic_istream::gcount()，示例

> 原文:[https://www . geesforgeks . org/stdbasic _ is treamgcount-in-c-with-examples/](https://www.geeksforgeeks.org/stdbasic_istreamgcount-in-c-with-examples/)

**STD::basic _ is tream::gcount()**用于对给定字符串中的字符进行计数。它返回上次无格式输入操作提取的字符数。无格式输入操作由这些函数返回: [get()](https://www.geeksforgeeks.org/fgets-gets-c-language/) 、 [getline()](https://www.geeksforgeeks.org/getline-string-c/) 、 [ignore()](https://www.geeksforgeeks.org/clearing-the-input-buffer-in-cc/) 、peek()、 [read()](https://www.geeksforgeeks.org/input-output-system-calls-c-create-open-close-read-write/) 等。

**头文件:**

```cpp
<iostream>

```

**语法:**

```cpp
streamsize gcount() const

```

**参数:**该方法不接受任何参数。

**返回值:**返回上次无格式输入操作提取的字符数。

下面是说明**STD::basic _ is tream::g count()**的程序:

**程序 1:**

```cpp
// C++ code to illustrate std::gcount()

#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{

    // Initialise array of characters
    char arr[20];

    // Declare string stream
    istringstream stream("GeeksforGeeks");

    // Read the string in string stream
    stream.read(arr, sizeof arr);

    // Print the count of characters in
    // string "GeeksforGeeks"
    cout << "The count of characters"
         << " in the string "
         << " is " << stream.gcount()
         << endl;

    return 0;
}
```

**输出:**

```cpp
The count of characters in the string  is 13

```

**参考文献:**T2【http://www . cplusplus . com/reference/is tream/basic _ is tream/g count/