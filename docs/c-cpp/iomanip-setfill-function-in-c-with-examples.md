# iomanip setfill()函数在 C++ 中的使用示例

> 原文:[https://www . geesforgeks . org/iomanip-set fill-function-in-c-with-examples/](https://www.geeksforgeeks.org/iomanip-setfill-function-in-c-with-examples/)

C++ 中 **iomaip 库**的 **setfill()** 方法用于根据指定为该方法参数的字符设置 ios 库填充字符。

**语法:**

```cpp
setfill(char c)

```

**参数:**该方法接受 **c** 作为参数，该参数是要设置填充对应的字符参数。

**返回值:**这个方法不返回任何东西。它只充当流操纵器。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of setfill() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    cout << "Before setting the fill char: \n"
         << setw(10);
    cout << num << endl;

    // Using setfill()
    cout << "Setting the fill char"
         << " setfill to *: \n"
         << setfill('*')
         << setw(10);
    cout << num << endl;

    return 0;
}
```

**输出:**

```cpp
Before setting the fill char: 
        50
Setting the fill char setfill to *: 
********50

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of setfill() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    cout << "Before setting the fill char: \n"
         << setw(10);
    cout << num << endl;

    cout << "Setting the fill"
         << " char setfill to $: \n"
         << setfill('{content}apos;)
         << setw(10);
    cout << num << endl;

    return 0;
}
```

**输出:**

```cpp
Before setting the fill char: 
        50
Setting the fill char setfill to $: 
$$$$50

```

**参考:**T2】http://www.cplusplus.com/reference/iomanip/setfill/