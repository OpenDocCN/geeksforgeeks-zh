# ios clear()函数在 C++ 中的使用示例

> 原文:[https://www . geesforgeks . org/IOs-clear-function-in-c-with-examples/](https://www.geeksforgeeks.org/ios-clear-function-in-c-with-examples/)

C++ 中 **ios 类**的 **clear()** 方法是通过设置来改变指定标志的当前状态。因此这个函数改变了这个流的内部状态。

**语法:**

```cpp
void clear(iostate state)

```

**参数:**该方法接受 iostate 作为参数，该参数是要在该流中设置的标志位。它可以是好位、故障位、故障位或坏位。

**返回值:**这个方法不返回任何东西。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of clear() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;

    // Print the result
    cout << "is eofbit set: "
         << ss.eof() << endl;

    // Using clear() function
    ss.clear(ss.eofbit);

    cout << "clear() used to set eofbit "
         << endl;

    // Print the result
    cout << "is eofbit set: "
         << ss.eof() << endl;

    return 0;
}
```

**输出:**

```cpp
is eofbit set: 0
clear() used to set eofbit 
is eofbit set: 1

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of clear() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;

    // Print the result
    cout << "is failbit set: "
         << ss.fail() << endl;

    // Using clear() function
    ss.clear(ss.failbit);

    cout << "clear() used to set failbit "
         << endl;

    // Print the result
    cout << "is failbit set: "
         << ss.fail() << endl;

    return 0;
}
```

**输出:**

```cpp
is failbit set: 0
clear() used to set failbit 
is failbit set: 1

```

**参考:**T2【hhttp://www . cplusplus . com/Reference/IOs/IOs/clear/