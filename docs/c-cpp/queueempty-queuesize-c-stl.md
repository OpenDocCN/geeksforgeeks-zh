# c++ STL 中的队列::空()和队列::大小()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/queueempty-queueize-c-STL/

[队列](https://www.geeksforgeeks.org/queue-cpp-stl/)是一种以先进先出(先进先出)方式运行的容器适配器。元素从后面(末端)插入，从前面删除。

**queue::empty()**

empty()函数用于检查队列容器是否为空。

**语法:**

```cpp
*queuename*.empty()
Parameters :
No parameters are passed
Returns :
True, if list is empty
False, Otherwise

```

示例:

```cpp
Input :  myqueue = 1, 2, 3
         myqueue.empty();
Output : False

Input :  myqueue
         myqueue.empty();
Output : True

```

**错误和异常**

1.  如果传递了参数，则显示错误
2.  显示无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of empty() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    queue<int> myqueue;
    myqueue.push(1);

    // Queue becomes 1

    if (myqueue.empty()) {
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

**应用:**给定一个整数队列，求所有整数的和。

```cpp
Input  : 1, 8, 3, 6, 2
Output : 20

```

**算法**
1。检查队列是否为空，如果不是，将 front 元素添加到初始化为 0 的变量中，并弹出 front 元素。
2。重复此步骤，直到队列为空。
3。打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of empty() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    int sum = 0;
    queue<int> myqueue;
    myqueue.push(1);
    myqueue.push(8);
    myqueue.push(3);
    myqueue.push(6);
    myqueue.push(2);

    // Queue becomes 1, 8, 3, 6, 2

    while (!myqueue.empty()) {
        sum = sum + myqueue.front();
        myqueue.pop();
    }
    cout << sum;
    return 0;
}
```

输出:

```cpp
20

```

**queue::size()**

size()函数用于返回列表容器的大小或列表容器中的元素数量。

**语法:**

```cpp
*queuename*.size()
Parameters :
No parameters are passed
Returns :
Number of elements in the container

```

示例:

```cpp
Input :  myqueue = 1, 2, 3
         myqueue.size();
Output : 3

Input :  myqueue
         myqueue.size();
Output : 0

```

**错误和异常**

1.  如果传递参数，则显示错误。
2.  显示无异常抛出保证

```cpp
// CPP program to illustrate
// Implementation of size() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    int sum = 0;
    queue<int> myqueue;
    myqueue.push(1);
    myqueue.push(8);
    myqueue.push(3);
    myqueue.push(6);
    myqueue.push(2);

    // Queue becomes 1, 8, 3, 6, 2

    cout << myqueue.size();

    return 0;
}
```

输出:

```cpp
5

```

**应用:**给定一个整数队列，求所有整数的和。

```cpp
Input  : 1, 8, 3, 6, 2
Output : 20

```

**算法**
1。检查队列的大小是否为零，如果不是，将 front 元素添加到初始化为 0 的变量中，并弹出 front 元素。
2。重复此步骤，直到队列大小变为 0。
3。打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of empty() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    int sum = 0;
    queue<int> myqueue;
    myqueue.push(1);
    myqueue.push(8);
    myqueue.push(3);
    myqueue.push(6);
    myqueue.push(2);

    // Queue becomes 1, 8, 3, 6, 2

    while (myqueue.size() > 0) {
        sum = sum + myqueue.front();
        myqueue.pop();
    }
    cout << sum;
    return 0;
}
```

输出:

```cpp
20

```