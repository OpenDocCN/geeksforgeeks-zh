# c++ 中的复制构造函数与赋值运算符

> 原文:[https://www . geesforgeks . org/copy-constructor-vs-assignment-operator-in-c/](https://www.geeksforgeeks.org/copy-constructor-vs-assignment-operator-in-c/)

复制构造函数和赋值操作符类似，因为它们都用于使用另一个对象初始化一个对象。但是，它们之间有一些基本的区别:

<figure class="table">

| 复制构造函数 | assigning operator |
| --- | --- |
| It is called when a new object is created from an existing object as a copy of the existing object. | This operator is called when an initialized object is assigned a value from another existing object. |
| It creates a separate memory block for the new object. | It does not create separate memory blocks or new memory spaces. |
| It is an overloaded constructor. | Is a bitwise operator. |
| The C++ compiler implicitly provides a copy constructor if there is no copy constructor defined in the class. | If the assignment operator is not overloaded, a bitwise copy is created. |
| **语法:**class name(cont class name&obj){

//body} | **语法:**className obj1、obj 2；obj 2 = obj 1； |

</figure>

考虑下面的 C++ 程序。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP Program to demonstrate the use of copy constructor
// and assignment operator
#include <iostream>
#include <stdio.h>
using namespace std;

class Test {
public:
    Test() {}
    Test(const Test& t)
    {
        cout << "Copy constructor called " << endl;
    }

    Test& operator=(const Test& t)
    {
        cout << "Assignment operator called " << endl;
        return *this;
    }
};

// Driver code
int main()
{
    Test t1, t2;
    t2 = t1;
    Test t3 = t1;
    getchar();
    return 0;
}
```

**Output**

```cpp
Assignment operator called 
Copy constructor called 
```

**说明:**这里，**T2 = T1；**调用**赋值运算符**，同**T2 . operator =(t1)；**和**测试 t3 = t1**调用**复制构造函数**，同**测试 T3(t1)；**

**必读:**[c++ 中什么时候调用复制构造函数？](https://www.geeksforgeeks.org/when-is-a-copy-constructor-called-in-cpp/)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。