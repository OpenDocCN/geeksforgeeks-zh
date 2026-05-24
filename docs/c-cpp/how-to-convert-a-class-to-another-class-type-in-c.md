# 如何在 C++ 中将一个类转换成另一个类类型？

> 原文:[https://www . geesforgeks . org/如何将一个类转换为另一个类-类型-in-c/](https://www.geeksforgeeks.org/how-to-convert-a-class-to-another-class-type-in-c/)

**先决条件:**[c++ 中的类型转换](https://www.geeksforgeeks.org/reverse-a-string-in-java/)[高级 C++ |转换运算符](https://www.geeksforgeeks.org/advanced-c-conversion-operators/)
通过类转换，可以将属于特定类类型的数据分配给属于另一类类型的对象。
**例:**
设‘A’和‘B’两类。如果我们想将属于“A”类的细节分配给“B”类的对象，那么这可以通过–
来实现

> B(类 B 的对象)= A(类 A 的对象)
> 其中“=”已经为类类型“B”的对象重载。

类转换可以通过转换函数来实现，转换函数是通过使用[运算符重载来实现的。](https://www.geeksforgeeks.org/operator-overloading-c/)
**例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h>
using namespace std;

// Source class, i.e
// class that will be converted to another class
class Class_type_one {
    string a = "GeeksforGeeks";

public:
    // Member function which returns
    // string type data
    string get_string()
    {
        return (a);
    }

    // Member function to display
    void display()
    {
        cout << a << endl;
    }
};

// Destination class, i.e
// Class type to which source class will be converted
class Class_type_two {
    string b;

public:
    // Operator overloading which accepts data
    // of the Destination class and
    // assigns those data to the source class
    // Here it is for the conversion of
    // Class_type_two to Class_type_one
    void operator=(Class_type_one a)
    {
        b = a.get_string();
    }

    // Member function for displaying
    // the data assigned to b.
    void display()
    {
        cout << b << endl;
    }
};

int main()
{
    // Creating object of class Class_type_one
    Class_type_one a;

    // Creating object of class Class_type_two
    Class_type_two b;

    // CLass type conversion
    // using operator overloading
    b = a;

    // Displaying data of object
    // of class Class_type_one
    a.display();

    // Displaying data of object
    // of class Class_type_two
    b.display();

    return 0;
}
```

**Output**

```cpp
GeeksforGeeks
GeeksforGeeks
```