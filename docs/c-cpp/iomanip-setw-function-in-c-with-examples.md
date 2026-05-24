# iomanip setw()函数在 C++ 中的使用示例

> 原文:[https://www . geesforgeks . org/iomanip-setw-function-in-c-with-examples/](https://www.geeksforgeeks.org/iomanip-setw-function-in-c-with-examples/)

C++ 中 **iomanip 库**的 **setw()** 方法用于根据指定为该方法参数的宽度设置 ios 库字段宽度。

**语法:**

```cpp
setw(int n)
```

**参数:**该方法接受 **n** 作为参数，该参数是要设置字段宽度对应的整数参数。
**返回值:**这个方法不返回任何东西。它只充当流操纵器。

**例 1:**

## C++

```cpp
// C++ code to demonstrate
// the working of setw() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    cout << "Before setting the width: \n"
         << num << endl;

    // Using setw()
    cout << "Setting the width"
         << " using setw to 5: \n"
         << setw(5);

    cout << num << endl;

    return 0;
}
```

**Output:** 

```cpp
Before setting the width: 
50
Setting the width using setw to 5: 
   50
```

**例 2:**

## C++

```cpp
// C++ code to demonstrate
// the working of setw() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    cout << "Before setting the width: \n"
         << num << endl;

    // Using setw()
    cout << "Setting the width"
         << " using setw to 10: \n"
         << setw(10);

    cout << num << endl;

    return 0;
}
```

**Output:** 

```cpp
Before setting the width: 
50
Setting the width using setw to 10: 
        50
```

**参考:**T2http://www.cplusplus.com/reference/iomanip/setw/