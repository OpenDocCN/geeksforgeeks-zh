# 如何在容器类

中添加对象的引用

> 原文:[https://www . geesforgeks . org/如何添加容器中对象的引用类/](https://www.geeksforgeeks.org/how-to-add-reference-of-an-object-in-container-classes/)

我们都很熟悉 [C++ 中的一个**别名**。别名意味着某个实体的另一个名称。因此，引用变量是一个别名，是现有变量/对象等的另一个名称。](https://www.geeksforgeeks.org/c-plus-plus/)

下面是添加变量引用的程序:

```cpp
// C++ program to illustrate
// aliasing in variable

#include <bits/stdc++.h>
using namespace std;

void aliasing(int N)
{
    // Adding reference variable to
    // N using &
    int& a = N;

    // Print the value pointed by
    // reference variable
    cout << "Value of a: " << a << endl;

    // Update the value of N using
    // reference variable
    a = 100;

    cout << "After Update:" << endl;

    // Print the value of a and N
    cout << "Value of a :" << a << endl;
    cout << "Value of N :" << N << endl;
}

// Driver Code
int main()
{
    // Given number
    int N = 9;

    // Function Call
    aliasing(N);
    return 0;
}
```

**Output:**

```cpp
Value of a: 9
After Update:
Value of a :100
Value of N :100

```

**说明:**在上面的程序中，一个变量 **a** 是变量 **N** 的别名，也就是说我们给变量 **N** 取了另外一个名字。所以无论我们用**做什么，它也会影响 **N** ，反之亦然。
因此，当我们将 **a 的值更改为 100** 时，那么，N 的值也更改为 100。**

**<u>容器类中对象的引用</u> :**
上面的方法给任何变量取别名都是正确的，但是在[容器](https://www.geeksforgeeks.org/containers-cpp-stl/)的情况下，上面的方法会抛出[编译错误](https://www.geeksforgeeks.org/errors-in-cc/)，因为容器不能直接存储引用，但是有一种替代的方法可以做到这一点。 [C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 中的模板 [std::reference_wrapper](https://www.geeksforgeeks.org/reference_wrapper-in-cpp/) 用于引用 C++ 中的任何容器。 **std::reference_wrapper** 是一个类模板，它将引用包装在一个可复制、可赋值的对象中。它经常被用作一种机制，将引用存储在通常不能保存引用的标准容器(如[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)、[列表](https://www.geeksforgeeks.org/list-cpp-stl/)等)中。

下面是在容器类中添加对象引用的程序:

```cpp
// C++ program to illustrate aliasing
// in list containers in C++
#include <bits/stdc++.h>
using namespace std;
class gfg {
private:
    int a;

public:
    gfg(int a)
    {
        this->a = a;
    }
    void setValue(int a)
    {
        this->a = a;
    }
    int getValue()
    {
        return this->a;
    }
};

// Driver Code
int main()
{
    // Declare list with reference_wrapper
    list<reference_wrapper<gfg> > l;

    // Object of class gfg
    gfg obj(5);

    l.push_back(obj);

    // Print the value of a
    cout << "Value of a for object obj is "
         << obj.getValue() << endl;

    cout << "After Update" << endl;

    // Change the value of a for Object obj
    // using member function
    obj.setValue(700);

    // Print the value of a after Update
    cout << "Value of a for object obj is "
         << obj.getValue() << endl;

    cout << "\nValue stored in the list is ";
    for (gfg i : l)
        cout << i.getValue() << endl;
    return 0;
}
```

**Output:**

```cpp
Value of a for object obj is 5
After Update
Value of a for object obj is 700

Value stored in the list is 700

```

**说明:**
在上面的程序中，创建 gfg 类的对象时，调用构造函数，将变量 a 的值初始化为 5。我们已经将对象的引用存储在列表中，然后通过调用成员函数 **setValue()** 将变量 a 的值更改为 700。现在，当我们看到其引用存储在列表中的对象的属性 a 的值时。存储的值是 700。