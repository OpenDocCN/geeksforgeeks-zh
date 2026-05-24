# 标准::在 C++ 中更大，示例

> 原文:[https://www . geesforgeks . org/STD greater-in-c-with-examples/](https://www.geeksforgeeks.org/stdgreater-in-c-with-examples/)

**std::greater** 是用于执行比较的功能对象。它被定义为大于不等式比较的函数对象类。这可用于改变给定功能的功能。这也可以用于各种标准算法，如[排序](https://www.geeksforgeeks.org/sort-c-stl/)、[优先级队列](https://www.geeksforgeeks.org/priority-queue-set-1-introduction/)等。

**头文件:**

```cpp
#include <functional.h>

```

**模板类:**

```cpp
template <class T> struct greater;

```

**参数:** **T** 是一种通过函数调用进行比较的参数类型。

**返回值:**返回如下所示的布尔变量:

*   **真:**如果两个元素说(a & b)这样一个> b
*   **假:**若甲<乙

下面是 C++ 中 **std::大于**的图解:

**程序 1:**

```cpp
// C++ program to illustrate std::greater

#include <algorithm>
#include <functional>
#include <iostream>
using namespace std;

// Function to print array elements
void printArray(int arr[], int n)
{

    for (int i = 0; i < n; i++) {
        cout << arr[i] << ' ';
    }
}

// Driver Code
int main()
{

    int arr[] = { 60, 10, 80, 40, 30,
                  20, 50, 90, 70 };
    int n = sizeof(arr) / sizeof(arr[0]);

    // To sort the array in decreasing order
    // use greater <int>() as an third arguments
    sort(arr, arr + 9, greater<int>());

    // Print array elements
    printArray(arr, n);

    return 0;
}
```

**Output:**

```cpp
90 80 70 60 50 40 30 20 10

```

**程序 2:**

```cpp
// C++ program to illustrate std::greater

#include <functional>
#include <iostream>
#include <queue>
using namespace std;

// Function to print elements of priority_queue
void showpq(priority_queue<int, vector<int>,
                           greater<int> >
                pq)
{
    priority_queue<int,
                   vector<int>,
                   greater<int> >
        g;
    g = pq;

    // While priority_queue is not empty
    while (!g.empty()) {

        // Print the top element
        cout << g.top() << ' ';

        // Pop the top element
        g.pop();
    }
}

// Driver Code
int main()
{
    // priority_queue use to implement
    // Max Heap, but using function
    // greater <int> () it implements
    // Min Heap
    priority_queue<int, vector<int>,
                   greater<int> >
        gquiz;

    // Inserting Elements
    gquiz.push(10);
    gquiz.push(30);
    gquiz.push(20);
    gquiz.push(5);
    gquiz.push(1);

    // Print elements of priority queue
    cout << "The priority queue gquiz is : ";
    showpq(gquiz);
    return 0;
}
```

**Output:**

```cpp
The priority queue gquiz is : 1 5 10 20 30

```