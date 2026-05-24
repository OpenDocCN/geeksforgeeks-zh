# c++ 中类与类之间的相互友谊示例

> 原文:[https://www . geeksforgeeks . org/c 类相互友谊示例/](https://www.geeksforgeeks.org/mutual-friendship-of-classes-in-c-with-examples/)

**先决条件:**[c++ 中的好友类](https://www.geeksforgeeks.org/friend-class-function-cpp/)
A [好友类](https://www.geeksforgeeks.org/friend-class-function-cpp/)可以访问其声明为好友的其他类的[私有和受保护成员](https://www.geeksforgeeks.org/difference-between-private-and-protected-in-c-with-example/)。有时允许一个特定的类访问另一个类的私有成员是有用的。
下面是说明朋友类的程序:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate friend class
#include <iostream>
using namespace std;

// Class A
class A {
private:
    // Private member of Class A
    int a;

public:
    // Constructor to initialise private
    // member of class A
    A() { a = 0; }

    // Make friend class B using a friend
    // keyword
    friend class B;
};

// Class B
class B {
private:
    // Private members of class B
    int b;

public:
    // Members function of class B
    void showA(A& x)
    {
        // Since B is friend of A,
        // it can access private members
        // of class A
        cout << "Accessed Private "
             << "Member of class A\n";
        cout << "A::a = " << x.a;
    }
};

int main()
{
    // Object of class A
    A a;

    // Object of class B
    B b;

    // Member function of friend class B
    b.showA(a);
    return 0;
}
```

**Output:** 

```cpp
Accessed Private Member of class A
A::a = 0
```

**类的相互友谊:**对于 A 类和 B 类来说，如果 A 类是 B 类的朋友类，B 类是 A 类的朋友类，则称之为相互友谊，由于这两个类之间建立了友谊，因此两个类都可以使用自己的成员函数访问彼此受保护的私有成员。
在这两个类中正常进行函数的声明和定义时，会遇到一个常见的[语法错误](https://www.geeksforgeeks.org/errors-in-cc/)，这表明首先声明的类即使成为朋友也不能访问后续类的数据成员。
所以**友谊不是相互的**。如果**A 类**是 **B 类**的朋友，那么 **B 类**不会自动成为**A 类**的朋友。
但是我们可以通过避免上面发生的错误来建立类之间的相互友谊，第一个类中正在访问第二个类的数据成员的函数是在第二个类之后使用[范围解析运算符](https://www.geeksforgeeks.org/scope-resolution-operator-in-c/)定义的。
我们假设**A 类**在程序中最先定义，**B 类**在**A 类**之后定义。**A 类**中访问**B 类**数据的成员函数应定义在**B 类**之后。这样做是为了确保编译器首先读取**B 类**，后者反过来会向编译器提供信息，说明**A 类**是**B 类**的朋友，因此被允许访问其成员。
下面是说明班级相互友谊的程序:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate mutual
// friendship of classes
#include <iostream>
using namespace std;

// Forward Declaration
class B;

// Class A
class A {

    // Member of class A
    int data;

public:
    // Make B as a friend of class A
    friend class B;

    // Constructor to initialise member
    // of class A
    A(int d) { data = d; }

    // Function to get data of friend
    // class B
    void get_data_B(B objb);
};

// Class B
class B {

    // Member of class B
    int dataB;

public:
    // Making A a friend of class B
    friend class A;

    // Constructor to initialise member of
    // class B
    B(int d) { dataB = d; }

    // Function to get the data of
    // friend class A
    void get_data_A(A obja)
    {
        cout << "Data of A is: "
             << obja.data;
    }
};

// Function for accessing friend class
// B's object
void A::get_data_B(B objb)
{
    cout << "Data of B is: "
         << objb.dataB;
}

// Driver Code
int main()
{

    // Object of class A
    A a(10);

    // Object of class B
    B b(20);

    // Print data of class A
    b.get_data_A(a);
    cout << endl;

    // Print data of class B
    a.get_data_B(b);
    return 0;
}
```

**Output:** 

```cpp
Data of A is: 10
Data of B is: 20
```

在上面的程序中作为**A 类**和**B 类**是共同的朋友。因此，访问 A 类的私有成员也可以从 B 类的成员函数中完成，访问 B 类的私有成员也可以从 A 类的成员函数中完成