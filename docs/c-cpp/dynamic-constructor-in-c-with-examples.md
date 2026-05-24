# c++ 中的动态构造函数，示例

> 原文:[https://www . geesforgeks . org/dynamic-constructor-in-c-with-examples/](https://www.geeksforgeeks.org/dynamic-constructor-in-c-with-examples/)

当在一个[构造器](https://www.geeksforgeeks.org/constructors-c/)中使用动态内存分配器[新](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/)动态完成内存分配时，它被称为**动态构造器**。通过使用这个，我们可以动态地初始化对象。
**例 1:**

## CPP14

```cpp
#include <iostream>
using namespace std;

class geeks {
    const char* p;

public:
    // default constructor
    geeks()
    {

        // allocating memory at run time
        p = new char[6];
        p = "geeks";
    }

    void display()
    {
        cout << p << endl;
    }
};

int main()
{
    geeks obj;
    obj.display();
}
```

**输出:**

```cpp
geeks
```

**解释**:这里我们指向类型为 **char** 的数据成员，该成员由**新的**运算符动态分配内存，当我们在类的构造函数中创建动态内存时，这被称为动态构造函数。
**例 2:**

## CPP14

```cpp
#include <iostream>
using namespace std;

class geeks {
    int* p;

public:
    // default constructor
    geeks()
    {

        // allocating memory at run time
        // and initializing
        p = new int[3]{ 1, 2, 3 };

        for (int i = 0; i < 3; i++) {
            cout << p[i] << " ";
        }

        cout << endl;
    }
};

int main()
{

    // five objects will be created
    // for each object
    // default constructor would be called
    // and memory will be allocated
    // to array dynamically
    geeks* ptr = new geeks[5];
}
```

**Output:** 

```cpp
1 2 3 
1 2 3 
1 2 3 
1 2 3 
1 2 3
```

动态地。
**解释**:在这个程序中我们动态的创建了对象数组。第一个对象是 ptr[0]，第二个对象是 ptr[1]等等。对于每个对象创建，调用默认构造函数，对于每个对象，内存由 [**新的**](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/) 操作符分配给指针类型变量。
**例 3:**

## CPP14

```cpp
#include <iostream>
using namespace std;

class geeks {
    int* p;

public:
    // default constructor
    geeks()
    {

        // allocating memory at run time
        p = new int;
        *p = 0;
    }

    // parameterized constructor
    geeks(int x)
    {
        p = new int;
        *p = x;
    }
    void display()
    {
        cout << *p << endl;
    }
};

int main()
{

    // default constructor would be called
    geeks obj1 = geeks();
    obj1.display();

    // parameterized constructor would be called
    geeks obj2 = geeks(7);
    obj2.display();
}
```

**Output:** 

```cpp
0
7
```

**说明:**在这个整数类型中，指针变量在类中声明，在调用构造函数时动态分配内存。当我们创建对象 **obj1** 时，会调用默认构造函数，并将内存动态分配给指针类型变量，并用值 0 初始化。类似地，当创建**对象 2** 时，调用参数化构造函数并动态分配内存。