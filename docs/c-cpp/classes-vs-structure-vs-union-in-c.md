# c++ 中类对结构对并集

> 原文:[https://www . geesforgeks . org/class-vs-structure-vs-union-in-c/](https://www.geeksforgeeks.org/classes-vs-structure-vs-union-in-c/)

[**类**](https://www.geeksforgeeks.org/c-classes-and-objects/) **:** 是用户自定义的[数据类型](https://www.geeksforgeeks.org/c-data-types/)，用[变量](https://www.geeksforgeeks.org/variables-in-c/)和[函数](https://www.geeksforgeeks.org/functions-in-c/)括起来。它就像是一个[物体](https://www.geeksforgeeks.org/c-classes-and-objects/)的蓝图。类成员默认为**私有**。例如，汽车是一个物体，它的颜色、设计、重量是它的属性，而刹车、限速等是它的属性。是它的功能。

**语法:**

```cpp
class <class_name>
{
     private:
     // Data members
     ........... ...... .......

     public:
     // Data members
     // Member function
     ......... ........ ......

     protected:
     // Data members
     // Member function
    ....... ....... ......
};
```

下面是 C++ 程序来说明类:

## c++

```cpp
// C++ program to illustrate class
#include <bits/stdc++.h>
using namespace std;

// Class with data members
// and member function
class Geeks {
public:
    string geekname;
    int roll_no;

    // Function printName
    // prints the name
    void printName()
    {
        cout << "Geekname is: "
             << geekname;
    }

    // Function printRollno
    // prints the roll no
    void printRollno()
    {
        cout << "Roll no  is: "
             << roll_no;
    }
};

// Driver Code
int main()
{

    // Object of class Geeks
    Geeks obj1;

    // Initialize a public data
    // members of class Geeks
    obj1.geekname = "Geek";
    obj1.roll_no = 15;

    // Function Call
    obj1.printName();
    cout << endl;

    // Function Call
    obj1.printRollno();

    return 0;
}
```

**输出:**

```cpp
Geekname is: Geek
Roll no  is: 15

```