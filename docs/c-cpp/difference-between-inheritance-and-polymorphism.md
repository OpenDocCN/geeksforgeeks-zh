# 遗传和多态性的区别

> 原文:[https://www . geeksforgeeks . org/继承和多态性的区别/](https://www.geeksforgeeks.org/difference-between-inheritance-and-polymorphism/)

[**继承**](https://www.geeksforgeeks.org/inheritance-in-c/) **:**
继承是创建一个新的类，继承已经存在的类的属性。它支持代码可重用性的概念，并减少了面向对象编程中的代码长度。
遗传类型有:

1.  单一继承
2.  多级继承
3.  多重继承
4.  混合遗传
5.  分级继承

**继承示例:**

## C++

```cpp
#include "iostream"
using namespace std;

class A {
    int a, b;

public:
    void add(int x, int y)
    {
        a = x;
        b = y;
        cout << (a + b) << endl;
    }
};

class B : public A {
public:
    void print(int x, int y)
    {
        add(x, y);
    }
};

int main()
{
    B b1;
    b1.print(5, 6);
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
class A {
    int a, b;
    public void add(int x, int y)
    {
        a = x;
        b = y;
        System.out.println("addition of a + b is:" + (a + b));
    }
}
class B extends A {
    public void sum(int x, int y)
    {
        add(x, y);
    }

    // Driver Code
    public static void main(String[] args)
    {
        B b1 = new B();
        b1.sum(5, 6);
    }
}
```

**输出:**

```cpp
addition of a+b is:11 
```

这里 B 类是继承基类 a 的属性( **add method** )的派生类，
[**【多态】**](https://www.geeksforgeeks.org/polymorphism-in-c/) **:**
多态是我们可以多种形式或方式执行一个任务。它适用于函数或方法。多态性允许对象决定在编译时和运行时实现哪种形式的函数。
多态性的类型有:

1.  编译时多态性(方法重载)
2.  运行时多态性(方法覆盖)

**多态性示例:**

## C++

```cpp
#include "iostream"
using namespace std;

class A {
    int a, b, c;

public:
    void add(int x, int y)
    {
        a = x;
        b = y;
        cout << "addition of a+b is:" << (a + b) << endl;
    }

    void add(int x, int y, int z)
    {
        a = x;
        b = y;
        c = z;
        cout << "addition of a+b+c is:" << (a + b + c) << endl;
    }

    virtual void print()
    {
        cout << "Class A's method is running" << endl;
    }
};

class B : public A {
public:
    void print()
    {
        cout << "Class B's method is running" << endl;
    }
};

int main()
{
    A a1;

    // method overloading (Compile-time polymorphism)
    a1.add(6, 5);

    // method overloading (Compile-time polymorphism)
    a1.add(1, 2, 3);

    B b1;

    // Method overriding (Run-time polymorphism)
    b1.print();
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
class A {
    int a, b, c;

    public void add(int x, int y)
    {
        a = x;
        b = y;
        System.out.println("addition of a+b is:" + (a + b));
    }

    public void add(int x, int y, int z)
    {
        a = x;
        b = y;
        c = z;
        System.out.println("addition of a+b+c is:" + (a + b + c));
    }

    public void print()
    {
        System.out.println("Class A's method is running");
    }
};

class B extends A {
    public void print()
    {
        System.out.println("Class B's method is running");
    }

    // Driver Code
    public static void main(String[] args)
    {
        A a1 = new A();

        // method overloading (Compile-time polymorphism)
        a1.add(6, 5);

        // method overloading (Compile-time polymorphism)
        a1.add(1, 2, 3);

        B b1 = new B();

        // Method overriding (Run-time polymorphism)
        b1.print();
    }
}
```

**输出:**

```cpp
addition of a+b is:11
addition of a+b+c is:6
Class B's method is running 
```

**遗传与多态性的区别:**

<figure class="table">

| s。不 | inheritance | Polymorphism |
| --- | --- | --- |
| 1。 | Inheritance refers to creating a new class (derived class) and inheriting the characteristics of the existing class (base class). | Polymorphism can be defined in many forms. |
| 2。 | Basically applicable to classes. | And it basically applies to functions or methods. |
| 3。 | Support the concept of reusability and reduce the code length in object-oriented programming. | Polymorphic objects are allowed to decide which form of function to implement at compile time (overloading) and run time (rewriting). |
| 4。 | Inheritance can be monogenic, heterozygous, polygenic, fractional and multilevel. | It can be compile-time polymorphism (overload) and runtime polymorphism (overlay). |
| 5。 | Used for pattern design. | It is also used for pattern design. |

</figure>