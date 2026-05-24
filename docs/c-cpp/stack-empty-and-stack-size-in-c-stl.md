# c++ STL 中的堆栈空()和堆栈大小()

> 原文:[https://www . geeksforgeeks . org/stack-empty-and-stack-size-in-c-STL/](https://www.geeksforgeeks.org/stack-empty-and-stack-size-in-c-stl/)

[堆叠](https://www.geeksforgeeks.org/stack-in-cpp-stl/)是一种后进先出(LIFO)工作方式的容器适配器，其中在一端添加一个新元素，并且(顶部)仅从该端移除一个元素。

**stack::empty()**

empty()函数用于检查堆栈容器是否为空。

**语法:**

```cpp
*stackname*.empty()
Parameters :
No parameters are passed.
Returns :
True, if stack is empty
False, Otherwise

```

示例:

```cpp
Input :   mystack
          mystack.empty();
Output :  True

Input :   mystack = 1, 2, 3
Output :  False

```

**错误和异常**

1.如果参数通过
2，显示错误。显示无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of empty() function
#include <iostream>
#include <stack>
using namespace std;

int main()
{
    stack<int> mystack;
    mystack.push(1);

    // Stack becomes 1

    if (mystack.empty()) {
        cout << "True";
    }
    else {
        cout << "False";
    }
    return 0;
}
```

输出:

```cpp
False

```

**应用:**
给定一堆整数，求所有整数的和。

```cpp
Input : 1, 8, 3, 6, 2
Output: 20

```

**算法**
1。检查堆栈是否为空，如果不是，将顶部元素添加到初始化为 0 的变量中，并弹出顶部元素。
2。重复此步骤，直到堆栈为空。
3。打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of empty() function
#include <iostream>
#include <stack>
using namespace std;

int main()
{
    int sum = 0;
    stack<int> mystack;
    mystack.push(1);
    mystack.push(8);
    mystack.push(3);
    mystack.push(6);
    mystack.push(2);

    // Stack becomes 1, 8, 3, 6, 2

    while (!mystack.empty()) {
        sum = sum + mystack.top();
        mystack.pop();
    }
    cout << sum;
    return 0;
}
```

输出:

```cpp
20

```

**stack::size()**

size()函数用于返回堆栈容器的大小或堆栈容器中的元素数量。

**语法:**

```cpp
*stackname*.size()
Parameters :
No parameters are passed.
Returns :
Number of elements in the container.

```

示例:

```cpp
Input :   mystack = 0, 1, 2
          mystack.size();
Output :  3

Input :   mystack = 0, 1, 2, 3, 4, 5
          mystack.size();
Output :  6

```

**错误和异常**

1.如果传递参数，则显示错误。
2。显示无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of size() function
#include <iostream>
#include <stack>
using namespace std;

int main()
{
    int sum = 0;
    stack<int> mystack;
    mystack.push(1);
    mystack.push(8);
    mystack.push(3);
    mystack.push(6);
    mystack.push(2);

    // Stack becomes 1, 8, 3, 6, 2

    cout << mystack.size();

    return 0;
}
```

输出:

```cpp
5

```

**应用:**
给定一堆整数，求所有整数的和。

```cpp
Input : 1, 8, 3, 6, 2
Output: 20

```

**算法**
1。检查堆栈的大小是否为零，如果不是，将顶部元素添加到初始化为 0 的变量中，并弹出顶部元素。
2。重复此步骤，直到堆栈大小变为 0。
3。打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of size() function
#include <iostream>
#include <stack>
using namespace std;

int main()
{
    int sum = 0;
    stack<int> mystack;
    mystack.push(1);
    mystack.push(8);
    mystack.push(3);
    mystack.push(6);
    mystack.push(2);

    // Stack becomes 1, 8, 3, 6, 2

    while (mystack.size() > 0) {
        sum = sum + mystack.top();
        mystack.pop();
    }
    cout << sum;
    return 0;
}
```

输出:

```cpp
20

```