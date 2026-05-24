# 用 C++ 实例化一个对象的不同方法，示例

> 原文:[https://www . geeksforgeeks . org/用示例实例化 c 中对象的不同方法/](https://www.geeksforgeeks.org/different-ways-to-instantiate-an-object-in-c-with-examples/)

**<u>先决条件:</u>** [C++ 类和对象](https://www.geeksforgeeks.org/c-classes-and-objects/)

**<u>实例化对象的不同方式</u>**

在 C++ 中，有不同的方法来实例化一个对象，其中一种方法是使用[构造函数。](https://www.geeksforgeeks.org/constructors-c/)这些是特殊的类成员，每次实例化该类的对象时，编译器都会调用它们。通过构造函数实例化对象有三种不同的方式:

1.  通过默认构造函数。
2.  通过参数化构造函数。
3.  通过复制构造函数。

**1。通过默认构造函数:**可以通过[默认构造函数](geeksforgeeks.org/c-internals-default-constructors-set-1/)以静态或动态方式实例化对象。

**语法:**

> **自动存储持续时间/静态初始化**
> 类名对象名；
> 
> **动态存储持续时间/动态初始化**T2】类名*对象名=新类名()；
> 
> **删除动态对象**
> 删除对象名称；

下面是通过默认构造函数演示对象实例化的 C++ 程序

## C++ 14

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Defining class example
class example {
    int x;

public:
    void set(int x)
    {
        this->x = x;
        cout << "The value of x is: "
             << x << "\n";
    }
};

// Driver code
int main()
{
    // Creating automatic storage object
    example obj1;
    obj1.set(5);

    // Creating dynamic storage object
    example* obj2 = new example();
    obj2->set(10);

    // Explicitly deleting the obj2
    delete obj2;

    return 0;
}
```

**Output**

> x 的值为:5
> x 的值为:10

**解释:**
在上面的代码中，有两种不同类型的实例化对象的方式-

1.  **示例 obj1:** 这一行正在实例化一个具有自动存储持续时间的对象。当此对象超出范围时，将被自动删除。
2.  **示例*obj2 =新示例():**这是实例化具有动态存储持续时间的对象的方式。此对象不会被自动删除。用户必须使用显式删除语句来删除对象。

> 删除 obj2

**2。通过参数化构造函数:**对象实例化可以通过[参数化构造函数](https://www.geeksforgeeks.org/constructors-c/)静态和动态完成。可以将参数传递给参数化构造函数。通常，这些参数有助于在创建对象时对其进行初始化。

**语法:**

> **静态初始化**
> 1。类名 objectname(参数)；
> 2。类名 objectname =类名(参数)；
> 
> **动态初始化**
> 类名*对象名=新类名(参数)；
> 
> **删除动态对象**
> 删除对象名称；

下面是演示参数化构造函数的 C++ 程序

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Defining the class example
class example {
    int x;

public:
    // Parameterized constructor
    example(int y)
    {
        x = y;
        cout << "The value of x is: "
             << x << "\n";
    }
};

// Driver code
int main()
{
    // Creating object with automatic
    // storage duration using Method 1
    example obj1(10);

    // Creating object with automatic
    // storage duration using Method 2
    example obj2 = example(8);

    // Creating object with dynamic
    // storage duration using Method 3
    example* obj3 = new example(20);

    delete obj3;
    return 0;
}
```

**Output**

> x 的值为:10
> x 的值为:8
> x 的值为:20

**解释:**
在上面的代码中，实例化一个对象有三种方式-

1.  **示例 obj1(10):** 这一行是使用具有自动存储持续时间的参数化构造函数实例化一个对象。当此对象超出范围时，将被自动删除。
2.  **示例 obj2 =示例(8):** 这一行是使用具有自动存储持续时间的参数化构造函数实例化对象。当此对象超出范围时，将被自动删除。
3.  **示例*obj3 =新示例(20):** 这是使用具有动态存储持续时间的参数化构造函数实例化对象的方式。此对象不会被自动删除。用户必须使用显式删除语句来删除对象。

**3。复制构造函数:**复制构造函数可用于静态或动态实例化对象。使用复制构造函数静态或动态初始化对象具有以下一般函数原型:

**语法:**

> **复制构造器**
> 类名(const 类名&old _ obj)；
> 
> **使用复制构造函数**
> **静态初始化**
> 1 实例化一个对象。类名 obj1
> 类名 obj2 = obj1
> 
> 2.类名称 obj1：
> 类名称 obj 2(obj 1)；
> 
> 动态初始化
> 1。class name * obj 1 = new class name()；
> classname *obj2 =新 class name(* obj 1)；

下面是演示复制构造函数的 C++ 程序

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Defining the class
class example {
    int x;

public:
    // Parameterized constructor
    example(int y)
    {
        x = y;
        cout << "The value of x is: "
             << x << "\n";
    }

    // Copy constructor
    example(example& obj)
    {
        x = obj.x;
        cout << "The value of x in "
             << "copy constructor: "
             << x << "\n";
    };
};

// Driver code
int main()
{
    // Instantiating copy constructor
    // using Method 1
    example obj1(4);
    example obj2 = obj1;

    // Instantiating copy constructor
    // using Method 2
    example obj3(obj1);

    // Instantiating copy constructor
    // using Method 3
    example* obj4 = new example(10);
    example* obj5 = new example(*obj4);

    delete obj5;
    delete obj4;
    return 0;
}
```

**Output**

> x 的值是:4
> 复制构造函数中 x 的值:4
> 复制构造函数中 x 的值:4
> x 的值是:10
> 复制构造函数中 x 的值:10

**解释:**
在上面的代码中，有三种使用复制构造函数实例化对象的方法-

1.  **方法 1:**
    *   **示例 obj1(4):** 这一行正在实例化一个具有自动存储持续时间的对象。
    *   **示例 obj2 = obj1:** 这一行调用复制构造函数，并创建一个新的对象 obj2，它是对象 obj1 的副本。
2.  **方法二:**
    *   **示例 obj3(obj1):** 这一行调用复制构造函数，并创建一个新的对象 obj3，它是对象 obj1 的副本。
3.  **方法 3:**
    *   **示例*obj4 =新示例(10):** 这是实例化具有动态存储持续时间的对象的方式。此对象不会被自动删除。用户必须使用显式删除语句来删除对象。
    *   **示例*obj5 =新示例(*obj4):** 该行调用复制构造函数，并创建一个新对象 obj5，它是对象 obj4 的副本。用户必须使用显式删除语句来删除对象。