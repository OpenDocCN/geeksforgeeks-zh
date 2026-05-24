# c++ STL 中的栈占位符()

> 原文:[https://www.geeksforgeeks.org/stack-emplace-in-c-stl/](https://www.geeksforgeeks.org/stack-emplace-in-c-stl/)

[堆叠](https://www.geeksforgeeks.org/stack-in-cpp-stl/)是一种后进先出(LIFO)工作方式的容器适配器，其中在一端添加一个新元素，并且(顶部)仅从该端移除一个元素。

**stack::emplace()**

此函数用于将新元素插入堆栈容器，新元素被添加到堆栈顶部。
**语法:**

```cpp
***stackname.emplace(value)***
Parameters :
The element to be inserted into the stack
is passed as the parameter.
Result :
The parameter is added to the stack 
at the top position.
```

示例:

```cpp
Input  : mystack{1, 2, 3, 4, 5};
         mystack.emplace(6);
Output : mystack = 6, 5, 4, 3, 2, 1

Input  : mystack{};
         mystack.emplace(4);
Output : mystack = 4
```

```cpp
Note: In stack container, the elements are printed in reverse order because the top is printed first then moving on to other elements.
```

**错误和异常**
1。它有很强的异常保证，因此，如果抛出异常，不会进行任何更改。
2。参数应该与容器的类型相同，否则会引发错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <stack>
using namespace std;

int main() {
  stack<int> mystack;
  mystack.emplace(1);
  mystack.emplace(2);
  mystack.emplace(3);
  mystack.emplace(4);
  mystack.emplace(5);
  mystack.emplace(6);
  // stack becomes 1, 2, 3, 4, 5, 6

  // printing the stack
  cout << "mystack = ";
  while (!mystack.empty()) {
    cout << mystack.top() << " ";
    mystack.pop();
  }
  return 0;
}
```

输出:

```cpp
6 5 4 3 2 1
```

**时间复杂度:** O(1)
**叠加::炮位()和叠加::推送()功能的区别。**
push()函数将*值*或传递给函数的参数的**副本**插入到顶部的容器中，而侵位()函数构造一个**新元素**作为参数的*值*，然后将其添加到容器的顶部。
**应用:**
给定若干个整数，使用侵位()将它们加到栈中，不用 size 函数就能求出栈的大小。

```cpp
Input : 5, 13, 0, 9, 4
Output: 5
```

**算法**
1。使用侵位()将给定元素逐个插入堆栈容器。
2。不断弹出堆栈元素，直到它变成空的，并增加计数器变量。
3。打印计数器变量。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Application of emplace() function
#include <iostream>
#include <stack>
using namespace std;

int main() {
  int c = 0;
  // Empty stack
  stack<int> mystack;
  mystack.emplace(5);
  mystack.emplace(13);
  mystack.emplace(0);
  mystack.emplace(9);
  mystack.emplace(4);
  // stack becomes 5, 13, 0, 9, 4

  // Counting number of elements in queue
  while (!mystack.empty()) {
    mystack.pop();
    c++ ;
  }
  cout << c;
}
```

输出:

```cpp
5
```