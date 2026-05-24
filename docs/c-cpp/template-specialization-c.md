# c++ 中的模板专门化

> 原文:[https://www.geeksforgeeks.org/template-specialization-c/](https://www.geeksforgeeks.org/template-specialization-c/)

[c++ 中的模板](https://www.geeksforgeeks.org/templates-cpp/)是一个特性。我们只编写一次代码，并将其用于任何数据类型，包括用户定义的数据类型。例如，sort()可以编写并用于对任何数据类型项进行排序。可以创建一个类堆栈，它可以用作任何数据类型的堆栈。
*如果我们想要特定数据类型的不同代码，该怎么办？*考虑一个大项目，它需要一个函数 sort()来处理许多不同数据类型的数组。让快速排序用于除字符之外的所有数据类型。在 char 的情况下，总的可能值是 256，计数排序可能是更好的选择。只有在对 char 数据类型调用 sort()时，才能使用不同的代码吗？
*在 C++ 中有可能获得特定数据类型的特殊行为。这叫做模板特殊化*。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A generic sort function
template <class T>
void sort(T arr[], int size)
{
    // code to implement Quick Sort
}

// Template Specialization: A function
// specialized for char data type
template <>
void sort<char>(char arr[], int size)
{
    // code to implement counting sort
}
```

另一个例子是类*集合*，它代表一组元素，支持并集、交集等操作。当元素的类型是 char 时，我们可能希望使用一个大小为 256 的简单布尔数组来组成一个集合。对于其他数据类型，我们必须使用一些其他复杂的技术。
***函数模板专门化示例程序***
例如，考虑下面的简单代码，其中我们对除 int 之外的所有数据类型都有通用模板 fun()。对于 int，有一个 fun()的专门版本。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

template <class T>
void fun(T a)
{
   cout << "The main template fun(): "
        << a << endl;
}

template<>
void fun(int a)
{
    cout << "Specialized Template for int type: "
         << a << endl;
}

int main()
{
    fun<char>('a');
    fun<int>(10);
    fun<float>(10.14);
}
```

输出:

```cpp
The main template fun(): a
Specialized Template for int type: 10
The main template fun(): 10.14
```

***类模板专门化示例程序***
在下面的程序中，为 int 数据类型编写了一个专门化版本的类 Test。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

template <class T>
class Test
{
  // Data members of test
public:
   Test()
   {
       // Initialization of data members
       cout << "General template object \n";
   }
   // Other methods of Test
};

template <>
class Test <int>
{
public:
   Test()
   {
       // Initialization of data members
       cout << "Specialized template object\n";
   }
};

int main()
{
    Test<int> a;
    Test<char> b;
    Test<float> c;
    return 0;
}
```

输出:

```cpp
Specialized template object
General template object
General template object
```

***模板专门化是如何工作的？***
当我们编写任何基于模板的函数或类时，只要编译器看到该函数/类正被用于新的数据类型或新的数据类型集(在多个模板参数的情况下)，编译器就会创建该函数/类的副本。
如果存在专用版本，编译器首先检查专用版本，然后检查主模板。编译器首先通过将传递的参数与专用版本中指定的数据类型进行匹配来检查最专用的版本。
如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息