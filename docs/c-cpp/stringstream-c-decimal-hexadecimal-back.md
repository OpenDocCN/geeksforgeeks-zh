# c++ 中的 StringStream 表示十进制到十六进制再回到

> 原文:[https://www . geeksforgeeks . org/string stream-c-十进制-十六进制-back/](https://www.geeksforgeeks.org/stringstream-c-decimal-hexadecimal-back/)

[Stringstream](https://www.geeksforgeeks.org/stringstream-c-applications/) 是 C++ 中的流类，用于对字符串进行操作。它可用于格式化/解析/将字符串转换为数字/字符等。
[Hex](https://www.geeksforgeeks.org/stdoct-stddec-and-stdhex-in-cpp/) 是一个 I/O 操纵器，它以对 I/O 流的引用为参数，并在操纵后返回对该流的引用。
以下是使用 stringstream 将任何十进制转换为十六进制的快速方法:

```cpp
// CPP program to convert integer to
// hexadecimal using stringstream and
// hex I/O manipulator.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int i = 942;
    stringstream ss;
    ss << hex << i;
    string res = ss.str();
    cout << "0x" << res << endl; // this will print 0x3ae
    return 0;
}
```

输出:

```cpp
0x3ae

```

如果我们想将十六进制字符串改回十进制，您可以通过以下方式实现:

```cpp
// CPP program to convert hexadecimal to
// integer using stringstream and
// hex I/O manipulator.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string hexStr = "0x3ae";
    unsigned int x;
    stringstream ss;
    ss << std::hex << hexStr;
    ss >> x;
    cout << x << endl; // this will print 942
    return 0;
}
```

输出:

```cpp
942

```