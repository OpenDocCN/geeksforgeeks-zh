# c++ STL 中的优先级 _ 队列值类型

> 原文:[https://www . geesforgeks . org/priority _ queue-value _ type-in-c-STL/](https://www.geeksforgeeks.org/priority_queue-value_type-in-c-stl/)

**priority_queue::value _ type**方法是 C++ STL 中的一个内置函数，它表示作为一个元素存储在 priority _ queue 中的对象类型。它充当模板参数的同义词。
**语法:**

```cpp
priority_queue::value_type variable_name
```

它没有参数，也没有返回值。
下面的程序说明了上述功能。
**节目 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// priority_queue :: value_type function
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    // declare value_type for priority queue
    priority_queue<int>::value_type AnInt;

    // Declares priority_queue
    priority_queue<int> q1;

    // here AnInt acts as a variable of int data type
    AnInt = 20;
    cout << "The value_type is AnInt = " << AnInt << endl;

    q1.push(AnInt);
    AnInt = 30;
    q1.push(AnInt);

    cout << "The element at the top of the priority_queue is "
         << q1.top() << "." << endl;

    return 0;
}
```

**Output:** 

```cpp
The value_type is AnInt = 20
The element at the top of the priority_queue is 30.
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    // declare value_type for priority queue
    priority_queue<string>::value_type AString;

    // Declares priority_queue
    priority_queue<string> q2;

    // here AnInt acts as a variable of int data type
    AString = "geeks for geeks";
    cout << "The value_type is AString = " << AString << endl;

    AString = "abc";
    q2.push(AString);
    AString = "def";
    q2.push(AString);
    AString = "ghi";
    q2.push(AString);

    cout << "Value stored in priority queue are :" << endl;
    while (!q2.empty()) {
        cout << '\t' << q2.top();
        q2.pop();
    }

    return 0;
}
```

**Output:** 

```cpp
The value_type is AString = geeks for geeks
Value stored in priority queue are :
    ghi    def    abc
```