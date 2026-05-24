# c++ 14 中的数字分隔符

> 原文:[https://www.geeksforgeeks.org/digit-separator-in-c14/](https://www.geeksforgeeks.org/digit-separator-in-c14/)

在本文中，我们将讨论数字分隔符在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中的使用。有时，阅读包含许多数字的数字变得很困难。比如 **1000** 可读但是如果加更多的零会怎么样，比如说 **1000000** ，现在读起来有点难，如果加更多的零会怎么样。现实生活中，数字中会加上逗号**()**。**例如:** **10，00，000** 。现在读起来很容易，就是十万。

现在问题来了，C++ 不接受这样的分隔符(逗号)，那么如何处理大数字呢？为了处理它， [**C++ 14**](https://www.geeksforgeeks.org/generalized-lambda-expressions-c14/) 引入了一个特性，它的名字是数字分隔符，用一个简单的引号 **(')** 表示。这可以使用户更容易阅读大量数据。

**程序 1:**

下面是在确定单引号的值时忽略单引号的实现:

## C++ 14

```cpp
// C++ program to demonstrate
// the above approach
#include <iostream>
using namespace std;

// Driver code
int main()
{
    long long int a = 10'00'000;

    // Print the value
    cout << a;

    return 0;
}
```

**Output**

```cpp
1000000
```

**程序 2:**

以下是显示单引号仅适用于用户的程序。在任何位置使用它们都不会影响编译器。

## C++ 14

```cpp
// C++ program to demonstrate
// the above approach
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    long long int a = 1'23'456;
    long long int b = 12'34'56;
    long long int c = 123'456;

    // Print all the value
    cout << "a:" << a << endl;
    cout << "b:" << b << endl;
    cout << "c:" << c << endl;

    return 0;
}
```

**Output**

```cpp
a:123456
b:123456
c:123456
```