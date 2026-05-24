# c++ 中的访问修饰符

> 原文:[https://www.geeksforgeeks.org/access-modifiers-in-c/](https://www.geeksforgeeks.org/access-modifiers-in-c/)

访问修饰符用于实现面向对象编程的一个重要方面，称为 [**【数据隐藏】**](https://practice.geeksforgeeks.org/problems/what-is-data-hiding) 。考虑一个现实生活中的例子:
研究和分析部门(R & AW)，有 10 个核心成员已经掌握了关于国家安全的敏感机密信息。现在我们可以将这些核心成员关联到一个类的数据成员或成员函数，这些数据成员或成员函数又可以关联到 R & A 翼。这 10 名成员可以直接从他们的分支(班级)访问机密信息，但是除了这 10 名成员之外的任何人都不能直接访问这些信息，即除了班级本身中流行的功能之外，其他功能都不能访问无权访问的信息。 既没有被分配的特权(如前面本文将看到的由 friend 类和继承类拥有的特权)，也没有被允许直接访问机密信息的这 10 个成员之一的访问权(类似于一个类的私有成员如何在外部世界通过直接访问私有成员的类的公共成员函数被访问)。 这就是数据隐藏在实践中的作用。
类[中的访问修饰符或访问说明符用于将可访问性分配给类成员。也就是说，它对类成员设置了一些限制，不让外部函数直接访问。
c++ 中有 3 种访问修饰符:](https://www.geeksforgeeks.org/c-classes-and-objects/)

1.  **公共**
2.  **私人**
3.  **受保护**

**注意**:如果我们没有为类内的成员指定任何访问修饰符，那么默认情况下，成员的访问修饰符将是**私有**。

现在让我们详细看看这些访问修饰符中的每一个:
**1。公共**:所有在公共说明符下声明的类成员对所有人都可用。声明为公共的数据成员和成员函数也可以被其他类和函数访问。使用直接成员访问运算符(，可以从程序中的任何位置访问类的公共成员。)与该类的对象关联。

**示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate public
// access modifier

#include<iostream>
using namespace std;

// class definition
class Circle
{
    public:
        double radius;

        double  compute_area()
        {
            return 3.14*radius*radius;
        }

};

// main function
int main()
{
    Circle obj;

    // accessing public datamember outside class
    obj.radius = 5.5;

    cout << "Radius is: " << obj.radius << "\n";
    cout << "Area is: " << obj.compute_area();
    return 0;
}
```

**输出:**

```cpp
Radius is: 5.5
Area is: 94.985
```

在上面的程序中，数据成员*半径*被声明为公共的，因此它可以在类外部被访问，因此被允许从 main()内部访问。
T3】2。私有:声明为*私有*的类成员只能被类内的成员函数访问。不允许类外的任何对象或函数直接访问它们。只允许成员函数或[朋友函数](https://www.geeksforgeeks.org/friend-class-function-cpp/)访问一个类的私有数据成员。

**示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate private
// access modifier

#include<iostream>
using namespace std;

class Circle
{  
    // private data member
    private:
        double radius;

    // public member function   
    public:   
        double  compute_area()
        {   // member function can access private
            // data member radius
            return 3.14*radius*radius;
        }

};

// main function
int main()
{  
    // creating object of the class
    Circle obj;

    // trying to access private data member
    // directly outside the class
    obj.radius = 1.5;

    cout << "Area is:" << obj.compute_area();
    return 0;
}
```

**输出**:

```cpp
 In function 'int main()':
11:16: error: 'double Circle::radius' is private
         double radius;
                ^
31:9: error: within this context
     obj.radius = 1.5;
         ^
```

上述程序的输出是一个编译时错误，因为我们不允许直接在类外访问类的私有数据成员。然而试图访问 obj.radius，radius 是一个私有数据成员，我们得到一个编译错误。

但是，我们可以使用类的公共成员函数间接访问类的私有数据成员。

**示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate private
// access modifier

#include<iostream>
using namespace std;

class Circle
{  
    // private data member
    private:
        double radius;

    // public member function   
    public:   
        void compute_area(double r)
        {   // member function can access private
            // data member radius
            radius = r;

            double area = 3.14*radius*radius;

            cout << "Radius is: " << radius << endl;
            cout << "Area is: " << area;
        }

};

// main function
int main()
{  
    // creating object of the class
    Circle obj;

    // trying to access private data member
    // directly outside the class
    obj.compute_area(1.5);

    return 0;
}
```

**输出**:

```cpp
Radius is: 1.5
Area is: 7.065
```

**3。Protected** : Protected 访问修饰符类似于 private 访问修饰符，除非在 friend 类的帮助下，否则不能在类外访问，不同的是声明为 Protected 的类成员也可以被该类的任何子类(派生类)访问。

**注**:这种通过继承的访问可以根据【继承】的[模式改变派生类中基类元素的访问修饰符](https://www.geeksforgeeks.org/inheritance-in-c/#Modes%20of%20Inheritance)。

**示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// protected access modifier
#include <bits/stdc++.h>
using namespace std;

// base class
class Parent
{  
    // protected data members
    protected:
    int id_protected;

};

// sub class or derived class from public base class
class Child : public Parent
{
    public:
    void setId(int id)
    {

        // Child class is able to access the inherited
        // protected data members of base class

        id_protected = id;

    }

    void displayId()
    {
        cout << "id_protected is: " << id_protected << endl;
    }
};

// main function
int main() {

    Child obj1;

    // member function of the derived class can
    // access the protected data members of the base class

    obj1.setId(81);
    obj1.displayId();
    return 0;
}
```

**输出**:

```cpp
id_protected is: 81
```