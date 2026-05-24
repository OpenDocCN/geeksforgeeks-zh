# c++ 中私有和受保护的区别，示例

> 原文:[https://www . geeksforgeeks . org/private-and-protected-in-c-with-example/](https://www.geeksforgeeks.org/difference-between-private-and-protected-in-c-with-example/)

<u>**[受保护](https://www.geeksforgeeks.org/access-modifiers-in-c/)**T5】</u>

受保护的访问修饰符类似于私有访问修饰符，不同之处在于声明为受保护的类成员在类外部不可访问，但它们可以被该类的任何子类(派生类)访问。

**例:**

```cpp
// C++ program to demonstrate
// protected access modifier

#include <bits/stdc++.h>
using namespace std;

// base class
class Parent {

    // protected data members
protected:
    int id_protected;
};

// sub class or derived class
class Child : public Parent {

public:
    void setId(int id)
    {

        // Child class is able to access the inherited
        // protected data members of the base class

        id_protected = id;
    }

    void displayId()
    {
        cout << "id_protected is: "
             << id_protected << endl;
    }
};

// main function
int main()
{

    Child obj1;

    // member function of the derived class can
    // access the protected data members of the base class

    obj1.setId(81);
    obj1.displayId();
    return 0;
}
```

**输出:**

```cpp
id_protected is: 81

```