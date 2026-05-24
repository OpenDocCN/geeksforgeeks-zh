# c++ 中抽象和封装的区别

> 原文:[https://www . geesforgeks . org/c 中抽象和封装的区别/](https://www.geeksforgeeks.org/difference-between-abstraction-and-encapsulation-in-c/)

[抽象](https://www.geeksforgeeks.org/abstraction-in-c/) :
在 OOPs 中，抽象是获取信息的方法，其中所需的信息将以最简单的方式获取，只提取所需的组件，而那些被认为不太重要的组件也不会被注意到。抽象的概念只向用户显示必要的信息。它通过隐藏程序的实现复杂性来降低程序的复杂性。
**抽象示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

class Summation {
private:
    // private variables
    int a, b, c;
public:
    void sum(int x, int y)
    {
        a = x;
        b = y;
        c = a + b;
        cout<<"Sum of the two number is : "<<c<<endl;
    }
};
int main()
{
    Summation s;
    s.sum(5, 4);
    return 0;
}
```

**输出:**

```cpp
Sum of the two number is: 9 
```

在这个例子中，我们可以看到抽象是通过使用类实现的。类“Summation”包含私有成员 a、b 和 c，这些成员只能由该类的成员函数访问。
[封装](https://www.geeksforgeeks.org/encapsulation-in-c/) :
封装是包含信息的过程或方法。封装是一种将数据隐藏在单个实体或单元中的方法，也是一种保护信息不受外界影响的方法。这个方法将数据和函数一起封装在一个类中，这也导致了数据抽象。
**封装示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

class EncapsulationExample {
private:
    // we declare a as private to hide it from outside
    int a;

public:
    // set() function to set the value of  a
    void set(int x)
    {
        a = x;
    }

    // get() function to return the value of a
    int get()
    {
        return a;
    }
};

// main function
int main()
{
    EncapsulationExample e1;

    e1.set(10);

    cout<<e1.get();
    return 0;
}
```

**输出:**

```cpp
10
```

在这个程序中，变量 a 是私有的，因此只能通过使用类中的 get()和 set()方法来访问和操作这个变量。因此，我们可以说，变量 a 和方法 set()以及 get()已经绑定在一起，这只是封装。
**抽象与封装的区别:**

<figure class="table">

| s。不 | abstract | encapsulation |
| --- | --- | --- |
| 1。 | Abstract is the process or method of obtaining information. | Encapsulation is a process or method that contains information. |
| 2。 | In abstraction, problems are solved at the design or interface level. | When packaging, the problem is solved at the implementation level. |
| 3。 | Abstraction is a way to hide unwanted information. | Encapsulation is a method of hiding data in a single entity or unit, and a method of protecting information from external attacks. |
| 4。 | We can use abstract classes and interfaces to implement abstraction. | Encapsulation can be realized by using access modifiers, that is, private, protected and public. |
| 5。 | In abstraction, abstract classes and interfaces are used to hide the complexity of implementation. | During encapsulation, the methods of acquirer and setter are used to hide data. |
| 6。 | Objects that help to perform abstraction are encapsulated. | While the encapsulated object does not need abstraction. |

</figure>