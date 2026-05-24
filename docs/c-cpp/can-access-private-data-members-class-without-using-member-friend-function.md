# 我们可以不使用成员或朋友函数访问类的私有数据成员吗？

> 原文:[https://www . geesforgeks . org/can-access-private-data-members-class-not-use-member-friend-function/](https://www.geeksforgeeks.org/can-access-private-data-members-class-without-using-member-friend-function/)

[封装](http://en.wikipedia.org/wiki/Encapsulation_(object-oriented_programming))的思想是将数据和方法(处理数据的方法)捆绑在一起，并限制类外私有数据成员的访问。在 C++ 中，朋友函数或朋友类也可以访问私有数据成员。

有没有可能在没有朋友的情况下访问班级外的私人成员？
是的，使用指针是可能的。以下面的程序为例。

```cpp
#include <iostream>
using namespace std;

class Test {
private:
    int data;

public:
    Test() { data = 0; }
    int getData() { return data; }
};

int main()
{
    Test t;
    int* ptr = (int*)&t;
    *ptr = 10;
    cout << t.getData();
    return 0;
}
```

**Output:**

```cpp
10

```

**例 2:**

```cpp
/*Program to initialize the private members and 
display them without using member functions.*/

#include <bits/stdc++.h>
using namespace std;

class A {
private:
    int x;
    int y;
};

int main()
{
    A a;
    int* p = (int*)&a;
    *p = 3;
    p++ ;
    *p = 9;
    p--;
    cout << endl
         << "x = " << *p;
    p++ ;
    cout << endl
         << "y = " << *p;
}
```

**Output:**

```cpp
x = 3
y = 9

```

**说明:**
在上面的程序中，a 是 a 类的对象，对象的地址通过应用类型转换赋给整数指针 p。指针 p 指向私有成员 x。整数值赋给*p，即 x。对象 a 的地址增加，通过访问内存位置，值 9 赋给 y。p–语句设置 x 的内存位置。使用 cout 语句，显示包含 x 的内容。

**例 3:**

```cpp
/*Program to initialize and display
private members using pointers.*/
#include <bits/stdc++.h>
using namespace std;

class A {
private:
    int x;
    int y;
};

class B : public A {
public:
    int z;

    void show(int* k)
    {
        cout << "x = " << *k << " y = " 
            << *(k + 1) << " z = " << *(k + 2);
    }
};

int main()
{
    B b; // object declaration
    int* p; // pointer declaration
    p = &b.z; // address of z is assigned to p
    *p = 3; // initialization of z
    p--; // points to previous location
    *p = 4; // initialization of y
    p--; // points to previous location
    *p = 5; // initialization of x
    b.show(p); // passing address of x to function show()

    return 0;
}
```

**Output:**

```cpp
x = 5 y = 4 z = 3

```

/*本代码由 [**舒巴姆·夏尔马**](https://auth.geeksforgeeks.org/user/auspicious_boy/profile) 贡献。*/

请注意，上述访问私有数据成员的方式根本不是一种推荐的访问成员的方式，永远不应该使用。此外，这并不意味着封装在 C++ 中不起作用。创建私有成员的想法是为了避免意外更改。上述数据变化并非偶然。这是故意编写的代码，用来愚弄编译器。

本文由 [**阿希什·库马尔**](http://www.linkedin.com/pub/ashish-kumar/5b/16/671) 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论