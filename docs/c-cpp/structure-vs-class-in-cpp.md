# c++ 中的结构与类

> 原文:[https://www.geeksforgeeks.org/structure-vs-class-in-cpp/](https://www.geeksforgeeks.org/structure-vs-class-in-cpp/)

在 C++ 中，一个结构与一个类相同，只是有一些不同。其中最重要的是**安全。**一个结构是不安全的，不能向最终用户隐藏其实现细节，而一个类是安全的，可以隐藏其编程和设计细节。**下面是一个类和一个结构之间的一些区别。**

<figure class="table">

| 

类

 | 

结构

 |
| --- | --- |
| A class member is private by default. | By default, members of the structure are public. |
| Memory allocation occurs on the heap. | Memory allocation occurs on the stack. |
| Class may have null values. | No structure member can have null values. |
| It is a data type of reference type. | It is the data type of a value type. |
| Use **class** keyword declaration. | Use the **struct** keyword declaration. |
| Class inheritance is possible. | There can be no inheritance in the structure. |
| Member variables of a class can be initiated directly. | Member variables of structures cannot be initialized directly. |

</figure>

**阐述这些差异的一些要点:**

**1)类的成员默认为私有，结构的成员默认为公共。**

例如，程序 1 编译失败，但程序 2 运行良好，

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Program 1
// CPP Program to demonstrate that Members of a class are
// private by default
#include <bits/stdc++.h>
using namespace std;

class Test {
    // x is private
    int x;
};

// Driver Code
int main()
{
    Test t;
    t.x = 20;
    // compiler error because x is private
    getchar();
    return 0;
}
```

**输出**

```cpp
prog.cpp: In function ‘int main()’:
prog.cpp:8:9: error: ‘int Test::x’ is private
    int x;
        ^
prog.cpp:13:7: error: within this context
    t.x = 20;
      ^
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Program 2
// CPP Program to demonstrate that members of a structure
// are public by default. 
#include <bits/stdc++.h>
using namespace std;

struct Test {
    // x is public
    int x;
};
int main()
{
    Test t;
    t.x = 20;
    // works fine because x is public
    cout << t.x;
    getchar();
    return 0;
}
```

**Output**

```cpp
20
```

**2)** 类使用**类**关键字声明，结构使用**结构**关键字声明。

**语法:**

```cpp
class ClassName {
private:
  member1;
  member2;
public:
  member3;
  .
  .
  memberN;
};
```

**语法:**

```cpp
struct structureName{
  member1;
  member2;
  .
  .
  .
  memberN;
};
```

**3)继承在类中是可能的，但在结构中是不可能的。**

例如，程序 3 工作正常，但程序 4 失败了，

## C++

```cpp
// Program 3
// C++ program to demonstrate Inheritance in class
#include <bits/stdc++.h>
using namespace std;

// Base class
class Parent {
public:
    int x;
};

// Sub class inheriting from Base Class(Parent)
class Child : public Parent {
public:
    int y;
};

// Driver Code
int main()
{

    Child obj1;
    // An object of class child has all data members
    // and member functions of class parent
    obj1.y = 7;
    obj1.x = 91;
    cout << obj1.y << endl;
    cout << obj1.x << endl;

    return 0;
}
```

**Output**

```cpp
7
91
```

## C++

```cpp
// Program 4
// C++ program to demonstrate Inheritance in structure
#include <iostream>
using namespace std;

struct Base {
public:
    int x;
};

struct Derived : Base {
public:
    int y;
}; // Is equivalent to struct Derived : public Base {}

int main()
{
    Derived d;
    d.x = 20; // Works fine because inheritance is public
    cout << d.x;
    getchar();
    return 0;
}
```

**必读:**[C 结构和 C++ 结构的区别](https://www.geeksforgeeks.org/difference-c-structures-c-structures/)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。