# c++ STL 中的栈顶()

> 原文:[https://www.geeksforgeeks.org/stack-top-c-stl/](https://www.geeksforgeeks.org/stack-top-c-stl/)

[栈](https://www.geeksforgeeks.org/stack-in-cpp-stl/)是一种具有后进先出(LIFO)工作类型的容器适配器，其中在称为栈顶的一端添加一个新元素，并且仅从同一端移除一个元素。

**堆栈::top()** top()函数用于引用堆栈的顶部(或最新的)元素。

**语法:**

```cpp
*stackname*.top()
```

**参数:**不需要任何值作为参数传递。
**返回值:**直接引用堆栈容器的顶部元素。

**示例:**

```cpp
Input  : stackname.push(5);
         stackname.push(1);
         stackname.top();
Output : 1

Input  : stackname.push(5);
         stackname.push(1);
         stackname.push(2);
         stackname.top();
Output : 2
```

**错误和异常**

1.  如果堆栈容器为空，会导致未定义的行为
2.  如果堆栈不为空，它保证无异常抛出

## C++

```cpp
// CPP program to illustrate
// Implementation of top() function
#include <iostream>
#include <stack>
using namespace std;

int main()
{
    stack<int> mystack;
    mystack.push(5);
    mystack.push(1);
    mystack.push(2);

    // Stack top
    cout << mystack.top();
    return 0;
}
```

**输出:**

```cpp
2
```

**应用:**
给定一堆整数，求所有整数的和。

```cpp
Input : 1, 8, 3, 6, 2
Output: 20
```

**算法**

1.  检查堆栈是否为空，如果不是，将顶部元素添加到初始化为 0 的变量中，并弹出顶部元素。
2.  重复此步骤，直到堆栈为空。
3.  打印变量的最终值。

## C++

```cpp
// CPP program to illustrate
// Application of top() function
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

**输出:**

```cpp
20 
```