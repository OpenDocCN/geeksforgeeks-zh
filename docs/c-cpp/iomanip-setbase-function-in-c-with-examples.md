# iomanip setbase()函数在 C++ 中的使用示例

> 原文:[https://www . geesforgeks . org/iomanip-setbase-function-in-c-with-examples/](https://www.geeksforgeeks.org/iomanip-setbase-function-in-c-with-examples/)

C++ 中 **iomaip 库**的 **setbase()** 方法用于根据指定为该方法参数的参数设置 ios 库 basefield 标志。

**语法:**

```cpp
setbase (int base)

```

**参数:**该方法接受**基数**作为参数，该参数是要设置基数对应的整数自变量。10 代表 dec，16 代表 hex，8 代表 oct，任何其他值代表 0(重置)。

**返回值:**这个方法不返回任何东西。它只充当流操纵器。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of setbase() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    cout << "Before set: \n"
         << num << endl;

    // Using setbase()
    cout << "Setting base to hex"
         << " using setbase: \n"
         << setbase(16)
         << num << endl;

    return 0;
}
```

**输出:**

```cpp
Before set: 
50
Setting base to hex using setbase: 
32

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of setbase() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    cout << "Before set: \n"
         << num << endl;

    // Using setbase()
    cout << "Setting base to oct"
         << " using setbase: \n"
         << setbase(8)
         << num << endl;

    return 0;
}
```

**输出:**

```cpp
Before set: 
50
Setting base to oct using setbase: 
62

```

**参考:**T2】http://www.cplusplus.com/reference/iomanip/setbase/