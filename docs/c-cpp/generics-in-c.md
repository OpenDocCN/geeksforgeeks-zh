# c++ 中的泛型

> 原文:[https://www.geeksforgeeks.org/generics-in-c/](https://www.geeksforgeeks.org/generics-in-c/)

泛型的思想是允许类型(整数、字符串、…等和用户定义的类型)成为方法、类和接口的参数。例如，像数组、映射等类，可以非常有效地使用泛型。我们可以将它们用于任何类型。

实现泛型编程的方法是为了提高代码的效率。通用编程使程序员能够编写适用于所有数据类型的通用算法。如果数据类型是整数、字符串或字符，则不需要创建不同的算法。

泛型编程的优点是

1.  代码可重用性
2.  避免函数重载
3.  一旦写好，就可以多次使用。

泛型可以使用[模板](https://www.geeksforgeeks.org/templates-cpp/)在 C++ 中实现。模板是一个简单而强大的 C++ 工具。简单的想法是将数据类型作为参数传递，这样我们就不需要为不同的数据类型编写相同的代码。例如，软件公司可能需要对不同的数据类型进行 sort()。我们可以编写一个 sort()并将数据类型作为参数传递，而不是编写和维护多个代码。

### 使用模板的通用函数:

我们编写了一个通用函数，可以用于不同的数据类型。函数模板的示例有 sort()、max()、min()、printArray()

```cpp
#include <iostream>
using namespace std;

// One function works for all data types.
// This would work even for user defined types
// if operator '>' is overloaded
template <typename T>

T myMax(T x, T y)
{
    return (x > y) ? x : y;
}

int main()
{

    // Call myMax for int
    cout << myMax<int>(3, 7) << endl;

    // call myMax for double
    cout << myMax<double>(3.0, 7.0) << endl;

    // call myMax for char
    cout << myMax<char>('g', 'e') << endl;

    return 0;
}
```

**Output:**

```cpp
7
7
g

```

### 使用模板的通用类:

像函数模板一样，类模板在类定义独立于数据类型的东西时很有用。对链接列表、二叉树、栈、队列、数组等类很有用。

下面是一个模板数组类的简单例子。

```cpp
#include <iostream>
using namespace std;

template <typename T>
class Array {
private:
    T* ptr;
    int size;

public:
    Array(T arr[], int s);
    void print();
};

template <typename T>
Array<T>::Array(T arr[], int s)
{
    ptr = new T[s];
    size = s;
    for (int i = 0; i < size; i++)
        ptr[i] = arr[i];
}

template <typename T>
void Array<T>::print()
{
    for (int i = 0; i < size; i++)
        cout << " " << *(ptr + i);
    cout << endl;
}

int main()
{
    int arr[5] = { 1, 2, 3, 4, 5 };
    Array<int> a(arr, 5);
    a.print();
    return 0;
}
```

**Output:**

```cpp
1 2 3 4 5

```

### 使用多类型泛型:

我们可以将多个数据类型作为参数传递给模板。下面的示例演示了相同的内容。

```cpp
#include <iostream>
using namespace std;

template <class T, class U>
class A {
    T x;
    U y;

public:
    A()
    {
        cout << "Constructor Called" << endl;
    }
};

int main()
{
    A<char, char> a;
    A<int, double> b;
    return 0;
}
```

**Output:**

```cpp
Constructor Called
Constructor Called

```