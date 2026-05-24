# 复杂物体及构图介绍

> 原文:[https://www . geesforgeks . org/复杂对象和组合简介/](https://www.geeksforgeeks.org/introduction-to-complex-objects-and-composition/)

对象是[面向对象编程](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/)的基本单位，代表现实生活中的实体。复杂对象是由较小的对象或对象的集合构建而成的对象。例如，移动电话由各种物体组成，如照相机、电池、屏幕、传感器等。在本文中，我们将了解复杂对象的使用和实现。
在面向对象编程语言中，对象组合用于相互之间具有**“has-a”**关系的对象。例如，手机有电池、传感器、屏幕等。因此，复杂的对象称为整体或父对象，而简单的对象通常称为子对象。在这种情况下，所有对象或组件都是共同组成复杂对象(移动)的子对象。

具有内置类型数据成员的类非常适合简单类。然而，在现实编程中，产品或软件由许多不同的更小的对象和类组成。在上面的例子中，移动电话由各种不同的物体组成，总体上构成了一个完整的移动电话。因为每个对象执行不同的任务，所以它们都在不同的类中维护。因此，这种复杂对象的概念被用在大多数现实场景中。使用这一概念的优点是:

*   每个单独的类都可以简单明了。
*   一个类可以专注于执行一个特定的任务并获得一个行为。
*   这个类更容易编写、调试、理解，也更容易被其他程序员使用。
*   虽然简单的类可以执行所有的操作，但是复杂的类可以被设计来协调简单类之间的数据流。
*   它降低了复杂对象的整体复杂性，因为复杂对象的主要任务是将任务委托给已经知道如何完成任务的子对象。

最重要的好处是，如果必须对子类进行任何更改，那么只能更改子类，而不能更改整个父类。

*   例如，如果我们想要更改移动对象中的电池类别，在合成的帮助下，更改仅在电池类别中进行，并且整个移动对象在更新的更改下工作正常。

**使用范围:**虽然没有明确的规则来说明程序员必须在什么时候使用组合，但根据经验，每个类都应该被构建来完成单个任务。任务应该是要么执行操作的某个部分，要么负责协调其他类，但不能同时执行这两个任务。这极大地增加了代码的维护和未来的更新，因为当我们希望更新一个特性或对象时，只需要更新与该特定功能相关的类。此外，很容易跟踪程序中的错误。例如:

## C++

```cpp
// C++ program to implement a
// composition

// A point class
class Point {
private:
    int x;
    int y;
};

// Every location has a point.
// Every point has two coordinates.
// The above class's functionality
// is only to store the coordinates
// in two variables. Any functionality
// using the points is implemented
// here
class Location {
    Private : Point Source;
    Point Destination
};
```

在这里给出的类中，**位置**使用类点的对象作为其数据成员。因此，位置是一个复杂的类，它使用一个简单的类点。让我们看看利用作文的程序。

下面是一个复合类的实现:

## C++

```cpp
// C++ program to implement a
// composite class
using namespace std;
#include <iostream>

// Class with a private parameter
// and the getters and setters
class One {

    // Private parameter
private:
    int num;

    // Public setter and getter
public:
    void set(int i)
    {
        num = i;
    }
    int get()
    {
        return num;
    }
};

// Another class
class Two {

    // Public method and the object
    // of the previous class
public:
    One O;
    void show()
    {
        cout << "\n Number = "
             << O.get();
    }
};

// Driver code
int main()
{
    // Creating the object of
    // class Two
    Two T;

    // Perform some operation using
    // the object of One in this class
    T.O.set(100);
    T.show();
}
```

**Output:** 

```cpp
Number = 100
```

**说明**:注意在程序中，二类有一个一类的对象。要访问一的成员，我们必须使用二的对象，如在命令集(100)中。此外，因为 num 是 One 的私有成员，所以我们必须使用公共函数来访问它的值。