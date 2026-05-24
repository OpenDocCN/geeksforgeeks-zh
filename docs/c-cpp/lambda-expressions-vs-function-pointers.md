# λ表达式与函数指针

> 原文:[https://www . geesforgeks . org/lambda-expressions-vs-function-pointers/](https://www.geeksforgeeks.org/lambda-expressions-vs-function-pointers/)

**函数指针:**[函数指针](https://www.geeksforgeeks.org/function-pointer-in-c/)，或子程序指针，或过程指针，是指向[函数](https://www.geeksforgeeks.org/functions-in-c/)的[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)。简单地说，它是指向文本部分内部位置的指针。它存储函数的[地址，并用于将一个行为作为参数传递给另一个函数。](https://www.geeksforgeeks.org/address-function-c-cpp/)

例如，如果有人想要对像[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)这样的容器或列表进行[排序，并使用](https://www.geeksforgeeks.org/selection-sort/) [STL sort( )](https://www.geeksforgeeks.org/sort-c-stl/) ，但不希望以升序排序，这是默认参数，在这种情况下，将行为传递给[排序函数](https://www.geeksforgeeks.org/selection-sort/)，这实际上是函数指针，并对他的数据进行排序。

**程序 1:** 下面是 [C++ 程序](https://www.geeksforgeeks.org/c-plus-plus/)来实现上面的概念:

## c++

```cpp
// C++ program to implement the above
// concepts
#include <bits/stdc++.h>
using namespace std;

// Descending order sorting function
int descending(int x, int y)
{
    return x > y;
}

// Absolute value sorting function
int absolute(int x, int y)
{
    return abs(x) > abs(y);
}

// Driver Code
int main()
{
    // Stores integers in the vector
    vector<int> vect = { 2, 8, -5, -9,
                         0, 12, 5 };

    cout << "Sorting with descending "
         << "order as parameter\n";

    // Stores the address of descending
    // order function in the funnptr
    // function pointer
    auto funptr = descending;

    // Pass pointer in the actual function
    sort(vect.begin(), vect.end(), funptr);

    // Print the vector
    for (auto i : vect)
        cout << i << " ";

    cout << "\n";

    cout << "Sorting with absolute order"
         << " as parameter \n";

    // Store the address of the absolute
    // value function in the funnptr1
    // function pointer
    auto funptr1 = absolute;

    // Pass pointer in actual function
    sort(vect.begin(), vect.end(), funptr1);

    // Print the vector
    for (auto i : vect) {
        cout << i << " ";
    }

    return 0;
}
```

**输出:**

```cpp
Sorting with descending order as parameter
12 8 5 2 0 -5 -9 
Sorting with absolute order as parameter 
12 -9 8 5 -5 2 0
```