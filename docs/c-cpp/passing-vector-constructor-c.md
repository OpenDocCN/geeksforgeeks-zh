# 在 C++ 中将向量传递给构造函数

> 原文:[https://www.geeksforgeeks.org/passing-vector-constructor-c/](https://www.geeksforgeeks.org/passing-vector-constructor-c/)

**当类成员是向量对象(不是引用)时。**

我们可以简单地在构造函数中赋值。

```cpp
// Passing vector object to a constructor.
#include <iostream>
#include <vector>
using namespace std;

class MyClass {
    vector<int> vec;

public:
    MyClass(vector<int> v) 
    {
       vec = v;
    }
    void print()
    {
        /// print the value of vector
        for (int i = 0; i < vec.size(); i++)
            cout << vec[i] << " ";
    }
};

int main()
{
    vector<int> vec;
    for (int i = 1; i <= 5; i++)
        vec.push_back(i);
    MyClass obj(vec);
    obj.print();
    return 0;
}
```

**Output:**

```cpp
1 2 3 4 5

```

我们也可以使用[初始化列表](https://www.geeksforgeeks.org/when-do-we-use-initializer-list-in-c/)进行初始化。

```cpp
// Initializing vector object using initializer
// list.
#include <iostream>
#include <vector>
using namespace std;

class MyClass {
    vector<int> vec;

public:
    MyClass(vector<int> v) : vec(v)
    {
    }
    void print()
    {
        /// print the value of vector
        for (int i = 0; i < vec.size(); i++)
            cout << vec[i] << " ";
    }
};

int main()
{
    vector<int> vec;
    for (int i = 1; i <= 5; i++)
        vec.push_back(i);
    MyClass obj(vec);
    obj.print();
    return 0;
}
```

**Output:**

```cpp
1 2 3 4 5

```

**当类成员是向量时，引用**。
在 C++ 中，[引用必须使用初始化列表](https://www.geeksforgeeks.org/when-do-we-use-initializer-list-in-c/)进行初始化。

```cpp
// CPP program to initialize a vector reference.
#include <iostream>
#include <vector>
using namespace std;

class MyClass {
    vector<int>& vec;

public:
    // this is the right way to assign
    // the reference of stl container
    MyClass(vector<int>& arr)
        : vec(arr)
    {
    }
    void print()
    {
        /// print the value of vector
        for (int i = 0; i < vec.size(); i++)
            cout << vec[i] << " ";
    }
};

int main()
{
    vector<int> vec;
    for (int i = 1; i <= 5; i++)
        vec.push_back(i);
    MyClass obj(vec);
    obj.print();
    return 0;
}
```

**Output:**

```cpp
1 2 3 4 5

```