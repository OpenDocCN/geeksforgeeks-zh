# 在 C++ STL 中堆叠 push()和 pop()

> 原文:[https://www.geeksforgeeks.org/stack-push-and-pop-in-c-stl/](https://www.geeksforgeeks.org/stack-push-and-pop-in-c-stl/)

[堆栈](https://www.geeksforgeeks.org/stack-in-cpp-stl/)是一种遵循**后进先出**属性的容器适配器，其中在一端添加一个新元素，而仅在该端移除一个元素(在顶部)。基本上，插入和删除发生在堆栈本身的顶部。

## 堆栈::推送()

push()函数用于在堆栈顶部插入或“推”一个元素。这是来自 [C++ 标准模板库(STL)](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的内置函数。该功能属于 **<栈>** 头文件。元素被添加到堆栈容器中，堆栈的大小增加 1。

**语法:**

```cpp
stackname.push(value)
```

**参数:**要插入的元素的值作为参数传递。

**结果:**添加一个与堆栈顶部传递的参数值相同的元素。

**例:**

```cpp
Input :   mystack
          mystack.push(6);
Output :  6

Input :   mystack
          mystack.push(0);
          mystack.push(1);
Output :  0, 1
```

**错误和异常:**

*   If the passed value does not match the stack type, an error is displayed.
*   If no exception is thrown by the parameter, the guarantee of no exception is displayed.

## CPP

```cpp
// CPP program to illustrate
// Implementation of push() function

#include <iostream>
#include <stack>
using namespace std;

int main()
{
    // Empty stack
    stack<int> mystack;
    mystack.push(0);
    mystack.push(1);
    mystack.push(2);

    // Printing content of stack
    while (!mystack.empty()) {
        cout << ' ' << mystack.top();
        mystack.pop();
    }
}
```

**输出**

```cpp
 2 1 0
```

> **注:**这里，输出是基于 LIFO 属性打印的。

## 堆栈::pop()

pop()函数用于从堆栈顶部移除或“弹出”元素(堆栈中最新或最顶层的元素)。这是一个来自 C++ 标准模板库(STL)的内置函数。该功能属于 **<栈>** 头文件。元素从堆栈容器中移除，堆栈的大小减少 1。

**语法:**

```cpp
stackname.pop()
```

**参数:**没有参数通过。

**结果:**移除堆栈中最新的元素或基本上顶部的元素。

**例:**

```cpp
Input :   mystack = 0, 1, 2
          mystack.pop();
Output :  0, 1

Input :   mystack = 0, 1, 2, 3, 4, 5
          mystack.pop();
Output :  0, 1, 2, 3, 4
```

**错误和异常:**

*   If the parameter is passed, an error is displayed.
*   Show no exception throw guarantee.

## CPP

```cpp
// CPP program to illustrate
// Implementation of pop() function

#include <iostream>
#include <stack>
using namespace std;

int main()
{
    stack<int> mystack;
    mystack.push(1);
    mystack.push(2);
    mystack.push(3);
    mystack.push(4);

   // Stack becomes 1, 2, 3, 4

    mystack.pop();
    mystack.pop();

   // Stack becomes 1, 2

    while (!mystack.empty()) {
        cout << ' ' << mystack.top();
        mystack.pop();
    }
}
```

**Output**

```cpp
 2 1
```

> **注:**这里，Output 是基于 LIFO 属性打印的。

**应用:**给定若干个整数，将它们加到栈中，不用 size 函数就能求出栈的大小。

```cpp
Input : 5, 13, 0, 9, 4
Output: 5
```

**算法:**

*   Push the given elements into the stack container one by one.
*   Eject the elements of the stack until the stack is empty, and increment the counter variable.
*   Print counter variables.

## CPP

```cpp
// CPP program to illustrate
// Application of push()
// and pop() function

#include <iostream>
#include <stack>
using namespace std;

int main()
{
    int c = 0;

    // Empty stack
    stack<int> mystack;
    mystack.push(5);
    mystack.push(13);
    mystack.push(0);
    mystack.push(9);
    mystack.push(4);
    // stack becomes 5, 13, 0, 9, 4

    // Counting number of elements in queue
    while (!mystack.empty()) {
        mystack.pop();
        c++ ;
    }
    cout << c;
}
```

**输出**

```cpp
5
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。