# c++ STL 中的 vector::at()和 vector::swap()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/vector swap-c-STL/

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。

**vector::at()**

at()函数用于引用出现在 ***位置*** 的元素，该位置作为函数的参数给出。
**语法:**

```cpp
***vectorname***.at(***position***)
Parameters: 
Position of the element to be fetched.
Returns: 
Direct reference to the element at the given position.
```

**示例:**

```cpp
Input: myvector = 1, 2, 3
         myvector.at(2);
Output: 3

Input: myvector = 3, 4, 1, 7, 3
         myvector.at(3);
Output: 7
```

**错误和异常**

1.  如果该位置不在向量中，它会将 ***抛出范围外*** 。
2.  否则，它具有很强的无异常抛出保证。

## C++

```cpp
// CPP program to illustrate
// Implementation of at() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector;
    myvector.push_back(3);
    myvector.push_back(4);
    myvector.push_back(1);
    myvector.push_back(7);
    myvector.push_back(3);
    cout << myvector.at(3);
    return 0;
}
```

**Output**

```cpp
7
```

**应用:**
给定一个整数向量，打印所有出现在偶数位置的整数。

```cpp
Input: 1, 2, 3, 4, 5, 6, 7, 8, 9
Output: 1 3 5 7 9
*Explanation - 1, 3, 5, 7 and 9 are at position 0, 2, 4, 6 and 8 which are even*
```

**算法**

1.  运行一个循环，直到向量的大小。
2.  检查该位置是否可被 2 整除，如果是，打印该位置的元素。

## C++

```cpp
// CPP program to illustrate
// Application of at() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector;
    myvector.push_back(1);
    myvector.push_back(2);
    myvector.push_back(3);
    myvector.push_back(4);
    myvector.push_back(5);
    myvector.push_back(6);
    myvector.push_back(7);
    myvector.push_back(8);
    myvector.push_back(9);
    // vector becomes 1, 2, 3, 4, 5, 6, 7, 8, 9

    for (int i = 0; i < myvector.size(); i += 2) {

        cout << myvector.at(i);
        cout << " ";
    }

    return 0;
}
```

**Output**

```cpp
1 3 5 7 9 
```

**vector::swap()**

此函数用于将一个向量的内容与另一个相同类型的向量交换，向量的大小可能不同。

**语法:**

```cpp
***vectorname1***.swap(***vectorname2***)
Parameters:
The name of the vector with which
the contents have to be swapped.
Result: 
All the elements of the 2 vectors are swapped.
```

**示例:**

```cpp
Input: myvector1 = {1, 2, 3, 4}
         myvector2 = {3, 5, 7, 9}
         myvector1.swap(myvector2);
Output: myvector1 = {3, 5, 7, 9}
         myvector2 = {1, 2, 3, 4}

Input: myvector1 = {1, 3, 5, 7}
         myvector2 = {2, 4, 6, 8}
         myvector1.swap(myvector2);
Output: myvector1 = {2, 4, 6, 8}
         myvector2 = {1, 3, 5, 7}
```

**错误和异常**

1.  如果向量不是同一类型，它会抛出一个错误。
2.  否则它有一个基本的无异常抛出保证。

## C++

```cpp
// CPP program to illustrate
// Implementation of swap() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    // vector container declaration
    vector<int> myvector1{ 1, 2, 3, 4 };
    vector<int> myvector2{ 3, 5, 7, 9 };

    // using swap() function to swap
    // elements of vector
    myvector1.swap(myvector2);

    // printing the first vector
    cout << "myvector1 = ";
    for (auto it = myvector1.begin();
         it < myvector1.end(); ++ it)
        cout << *it << " ";

    // printing the second vector
    cout << endl
         << "myvector2 = ";
    for (auto it = myvector2.begin();
         it < myvector2.end(); ++ it)
        cout << *it << " ";
    return 0;
}
```

**Output**

```cpp
myvector1 = 3 5 7 9 
myvector2 = 1 2 3 4 
```

如果向量的大小不同:

## C++

```cpp
// CPP program
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> vec1{ 100, 100, 100 };
    vector<int> vec2{ 200, 200, 200, 200, 200 };

    vec1.swap(vec2);

    cout << "The vec1 contains:";
    for (int i = 0; i < vec1.size(); i++)
        cout << ' ' << vec1[i];
    cout << '\n';

    cout << "The vec2 contains:";
    for (int i = 0; i < vec2.size(); i++)
        cout << ' ' << vec2[i];
    cout << '\n';

    return 0;
}
```

**Output**

```cpp
The vec1 contains: 200 200 200 200 200
The vec2 contains: 100 100 100
```