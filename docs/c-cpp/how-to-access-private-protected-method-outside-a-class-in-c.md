# 如何在 C++ 中访问类外的私有/受保护方法

> 原文:[https://www . geeksforgeeks . org/如何访问-私有-受保护-方法-c 中类外/](https://www.geeksforgeeks.org/how-to-access-private-protected-method-outside-a-class-in-c/)

**先决条件:**[c++ 中的访问修饰符](https://www.geeksforgeeks.org/access-modifiers-in-c/)[运行时多态性](https://www.geeksforgeeks.org/polymorphism-in-c/)

**Private:** 声明为 *private 的类成员*只能被类内部的函数访问。不允许类外的任何对象或函数直接访问它们。只允许成员函数或[朋友函数](https://www.geeksforgeeks.org/friend-class-function-cpp/)访问一个类的私有数据成员。

我们可以使用[虚函数](https://www.geeksforgeeks.org/pure-virtual-functions-and-abstract-classes/)访问其他类中的私有方法，虚函数是在基类中声明的成员函数，并由派生类重新定义(重写)。使用指针或对基类的引用来引用派生类对象可以调用该对象的虚拟函数，并执行该函数的派生类版本。

**程序 1:** 演示私有访问修饰符

## C++

```cpp
// C++ program to demonstrate private
// access modifier
#include <iostream>
using namespace std;

// Parent class having virtual
// function disp()
class Parent {
public:
    // Create virtual function
    virtual void disp()
    {
        cout << "This is the public disp"
             << " method of Parent class" << endl;
    }
};

// Child class inherit to parent class
class Child : public Parent {
private:
    int secret_key;

    // Private method which will be called
    // Override the method of parent class
    void disp()
    {
        cout << "This is the private disp "
             << "method of child class "
             << endl;
        cout << "The key is "
             << secret_key << endl;
    }

public:
    // Constructor of the child class
    Child(int key) { secret_key = key; }
};

// Driver Code
int main()
{
    // Create object of child class
    Child child(1019);

    // Upcasting
    Parent* obj = &child;

    // Function call of child class
    obj->disp();
    return 0;
}
```

**Output:** 

```cpp
This is the private disp method of child class 
The key is 1019
```

**说明**:

在上面的程序中，父类有一个函数 **void disp()** ，这是一个**虚拟的**函数。子类创建了另一个同名的函数，即 void disp()，但该函数是私有的，这意味着它不允许被类外的任何对象或函数直接访问。在 [main()](https://www.geeksforgeeks.org/executing-main-in-c-behind-the-scene/) 中，我们首先创建一个子类的对象，并传递一个参数来初始化子类中的 **secret_key** 变量，然后，我们将子类对象的地址存储在一个基类指针中，这也称为**上推**。现在基类指针保存子类对象的地址，但是当使用基类指针调用函数时，它将只调用基类函数。但如果要它调用子类函数使基类函数**虚化**。这也称为**运行时多态性。**

**Protected:** Protected 访问修饰符与 private 访问修饰符类似，区别在于声明为 Protected 的类成员在类外不可访问，但可以被该类的任何子类(派生类)访问。

**程序 2:** 演示受保护的访问修饰符

## C++

```cpp
// C++ program to demonstrate protected
// access modifier
#include <iostream>
using namespace std;

// Parent class having virtual
// function disp()
class Parent {
public:
    // Create virtual function
    virtual void disp()
    {
        cout << "This is the public disp"
             << " method of Parent class"
             << endl;
    }
};

// Child class inherit to parent class
class Child : public Parent {
protected:
    int secret_key;

    // Private method which will be called
    // Override the method of parent class
    void disp()
    {
        cout << "This is the protected  disp "
             << "method of child class "
             << endl;
        cout << "The key is "
             << secret_key << endl;
    }

public:
    // Constructor of child class
    Child(int key) { secret_key = key; }
};

// Driver Code
int main()
{
    // Create object of child class
    Child child(1019);

    // Upcasting
    Parent* obj = &child;

    // Function call of child class
    obj->disp();
    return 0;
}
```

**Output:** 

```cpp
This is the protected  disp method of child class 
The key is 1019
```

**说明**:

在上例中，父类具有函数 **void disp()** ，这是一个**虚拟的**函数。子类创建了另一个同名的函数，即 void disp()，但该函数是私有的，这意味着它不允许被类外的任何对象或函数直接访问。在 main()中，我们首先创建一个子类的对象，并传递一个参数来初始化子类中的 secret_key 变量，然后将子类对象的地址存储在基类指针中，这也称为**上播**。现在基类指针保存子类对象的地址，但是当使用基类指针调用函数时，它将只调用基类函数。但如果要它调用子类函数使基类函数**虚化**。这也叫 [**运行时多态**](https://www.geeksforgeeks.org/virtual-functions-and-runtime-polymorphism-in-c-set-1-introduction/) **。**