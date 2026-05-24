# c++ STL 中的堆栈交换()

> 原文:[https://www.geeksforgeeks.org/stack-swap-in-c-stl/](https://www.geeksforgeeks.org/stack-swap-in-c-stl/)

[堆栈](https://contribute.geeksforgeeks.org/stackempty-and-stacksize-in-c-stl/)是一种具有后进先出(LIFO)工作类型的容器适配器，其中在一端添加一个新元素，并且(顶部)仅从该端移除一个元素。

**stack::swap()**

此函数用于将一个堆栈的内容与另一个相同类型的堆栈交换，但大小可能会有所不同。

**语法:**

```cpp
*stackname1*.swap(*stackname2*)
```

**参数:**内容必须与之交换的堆栈的名称。

**结果:**2 栈的所有元素被交换。

示例:

```cpp
contents of the stack from top to bottom are
Input  : mystack1 = {4, 3, 2, 1}
         mystack2 = {9, 7 ,5, 3}
         mystack1.swap(mystack2);
Output : mystack1 =  9, 7, 5, 3
         mystack2 =  4, 3, 2, 1

Input  : mystack1 = {7, 5, 3, 1}
         mystack2 = {8, 6, 4, 2}
         mystack1.swap(mystack2);
Output : mystack1 =  8, 6, 4, 2
         mystack2 =  7, 5, 3, 1

```

**注意:**在堆叠容器中，元素以相反的顺序打印，因为首先打印顶部，然后移动到其他元素。

```cpp
// CPP program to illustrate
// Implementation of swap() function
#include <stack>
#include <iostream>
using namespace std;

int main()
{
        // stack container declaration
    stack<int> mystack1;
    stack<int> mystack2;

       // pushing elements into first stack
    mystack1.push(1);
    mystack1.push(2);
    mystack1.push(3);
    mystack1.push(4);

       // pushing elements into 2nd stack
    mystack2.push(3);
    mystack2.push(5);
    mystack2.push(7);
    mystack2.push(9);

        // using swap() function to swap elements of stacks
    mystack1.swap(mystack2);

        // printing the first stack
    cout<<"mystack1 = ";
     while (!mystack1.empty()) {
        cout<<mystack1.top()<<" ";
        mystack1.pop();
    }

        // printing the second stack
    cout<<endl<<"mystack2 = ";
    while (!mystack2.empty()) {
        cout<<mystack2.top()<<" ";
        mystack2.pop();
    }
    return 0;
}
```

输出:

```cpp
mystack1 = 9 7 5 3
mystack2 = 4 3 2 1

```