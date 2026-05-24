# ios setstate()函数在 C++ 中的使用示例

> 原文:[https://www . geesforgeks . org/IOs-setstate-function-in-c-with-examples/](https://www.geeksforgeeks.org/ios-setstate-function-in-c-with-examples/)

C++ 中 **ios 类**的 **setstate()** 方法用于通过设置作为参数传递的标志来更改该流的当前状态。因此这个函数改变了这个流的内部状态。

**语法:**

```cpp
void setstate(iostate state)

```

**参数:**该方法接受 iostate 作为参数，该参数是要在该流中设置的 goodbit、failbit、eofbit 和 badbit 标志的组合。

**返回值:**这个方法不返回任何东西。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of setstate() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream 1
    stringstream ss;
    ss.clear(ss.goodbit);

    // Stream 2
    stringstream ss2;
    cout << "current stream: " << ss2.rdstate() << endl;

    // Using setstate() function
    ss2.setstate(ss.rdstate());

    // Print the result
    cout << "updated stream: " << ss2.rdstate() << endl;

    return 0;
}
```

**输出:**

```cpp
current stream: 0
updated stream: 0

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of setstate() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream 1
    stringstream ss;
    ss.clear(ss.failbit);

    // Stream 2
    stringstream ss2;
    cout << "current stream: " << ss2.rdstate() << endl;

    // Using setstate() function
    ss2.setstate(ss.rdstate());

    // Print the result
    cout << "updated stream: " << ss2.rdstate() << endl;

    return 0;
}
```

**输出:**

```cpp
current stream: 0
updated stream: 4

```

**参考:**T2【hhttp://www . cplusplus . com/Reference/IOs/IOs/setstate/