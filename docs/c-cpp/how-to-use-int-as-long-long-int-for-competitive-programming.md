# 如何在竞技编程中使用 int 作为 long long int？

> 原文:[https://www . geesforgeks . org/如何使用 int-as-long-long-int-for-competitive-programming/](https://www.geeksforgeeks.org/how-to-use-int-as-long-long-int-for-competitive-programming/)

很多时候[竞技编程](https://www.geeksforgeeks.org/how-to-prepare-for-competitive-programming/)题的输入约束大于 int 的极限。因此，需要使用 long int 甚至 long long int。这里让我们举两个例子，如果一个天真的用户写了正确的逻辑，但输入仍然没有被接受，我们可以知道哪里需要纠正。

**情况 1:** 大整数输入不将 int 重新定义为 long int
情况 2: 大整数输入将 int 重新定义为 long int

**情况 1:** 大整数输入，不将 int 重新定义为 long long int

**示例:**

## C++

```cpp
// C++ program to demonstrate Overflow in Implicit Conversion itself

// Importing input output libraries
#include <iostream>

using namespace std;

// Main driver method
int main()
{
    // 10 raised to the power of 10
    int x = 1e10;

    // Printing the number
    cout << x << endl;

    // As return type of main was integer type
    return 0;
}
```

**输出:**

```cpp
prog.cpp: In function ‘int main()’:
prog.cpp:5:10: warning: overflow in implicit constant conversion [-Woverflow]
 int x = 1e10; 
         ^
```

**输出解释**:

这是因为整数数据类型可以容纳的数字范围是 4 个字节，这意味着它可以容纳范围从-2，147，483，647 到 2，147，483，647 的整数。在我们的例子中，输出超过了一个变量可以容纳的最大整数，所以抛出一个隐式常量转换的警告。所以我们必须使用长数据类型，因为它可以容纳 8 个字节。为了纠正这种情况，我们需要重新定义 int。然而，当 main 的数据类型也改变时，程序仍然会抛出一个错误。所以把它们定义为 int，这样我们在比赛中的速度就可以提高。(ie)**#定义 int long long int** 。

**情况 2:** 大整数输入，重定义 int 为 long long int

**示例:**

## C++

```cpp
// C++ program to demonstrate longlongint approach

// Including all basic libraries
#include <bits/stdc++.h>
using namespace std;

// Main driver method with int32_t return type
int32_t main()
{
    // Calculating size of Integer data type
    // using sizeof() method
    cout << "size of int = " << sizeof(int) << '\n';

// Defining int as long long int
#define int long long int

    // Calculating new size of Integer data type
    // again using standard sizeof() method
    cout << "new size of int = " << sizeof(int) << '\n';

    // Big custom input integer
    int x = 1e18;

    // Print and display this big integer value
    cout << "value of x = " << x << endl;

    return 0;
}
```

**Output**

```cpp
size of int = 4
new size of int = 8
value of x = 1000000000000000000
```

> **注意:**这通常用于竞争性编程问题，因为它将接受所有输入大小。