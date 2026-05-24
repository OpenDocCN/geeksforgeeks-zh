# C++ 中每个循环的

> 原文:[https://www.geeksforgeeks.org/for_each-loop-c/](https://www.geeksforgeeks.org/for_each-loop-c/)

除了[通用循环技术](https://www.geeksforgeeks.org/decision-making-c-c-else-nested-else/)，例如“for，while 和 do-while”，C++ 在其语言中还允许我们使用另一种功能来解决被称为“for-each”循环的相同目的。这个循环接受一个在每个容器元素上执行的函数。该循环在头文件“算法”中定义:***#包括<算法>*** ，因此必须包括该循环才能成功运行。

*   它是多功能的，即可以与任何容器一起工作。
*   它减少了使用泛型 for 循环提交错误的机会
*   它使代码更易读
*   for_each 循环提高了代码的整体性能

**语法:**

```cpp
for_each (InputIterator start_iter, InputIterator last_iter, Function fnc)

start_iter : The beginning position 
from where function operations has to be executed.
last_iter : The ending position 
till where function has to be executed.
fnc/obj_fnc : The 3rd argument is a function or 
an object function which operation would be applied to each element. 
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the
// working of for_each loop

#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

// helper function 1
void printx2(int a)
{
    cout << a * 2 << " ";
}

// helper function 2
// object type function
struct Class2
{
    void operator() (int a)
    {
        cout << a * 3 << " ";
    }
} ob1;

int main()
{

    // initializing array
    int arr[5] = { 1, 5, 2, 4, 3 };

    cout << "Using Arrays:" << endl;

    // printing array using for_each
    // using function
    cout << "Multiple of 2 of elements are : ";
    for_each(arr, arr + 5, printx2);

    cout << endl;

    // printing array using for_each
    // using object function
    cout << "Multiple of 3 of elements are : ";
    for_each(arr, arr + 5, ob1);

    cout << endl;

    // initializing vector
    vector<int> arr1 = { 4, 5, 8, 3, 1 };

    cout << "Using Vectors:" << endl;

    // printing array using for_each
    // using function
    cout << "Multiple of 2 of elements are : ";
    for_each(arr1.begin(), arr1.end(), printx2);

    cout << endl;

    // printing array using for_each
    // using object function
    cout << "Multiple of 3 of elements are : ";
    for_each(arr1.begin(), arr1.end(), ob1);

    cout << endl;

}
```

**Output**

```cpp
Using Arrays:
Multiple of 2 of elements are : 2 10 4 8 6 
Multiple of 3 of elements are : 3 15 6 12 9 
Using Vectors:
Multiple of 2 of elements are : 8 10 16 6 2 
Multiple of 3 of elements are : 12 15 24 9 3 
```

**例外和每种情况:**

在异常的情况下，如果函数抛出异常或者迭代器上的任何操作抛出异常，那么每个循环的**也将抛出异常，并且**中断/终止**循环。**

**注:**

*   无效参数可能导致[未定义的行为](https://www.geeksforgeeks.org/undefined-behavior-c-cpp/)。
*   For_each 不能处理数组的指针(数组指针不知道其大小，for_each 循环在不知道数组大小的情况下不能处理数组)

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working
// of for_each with Exception

#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

// Helper function 1
void printx2(int a)
{
    cout << a * 2 << " ";
    if ( a % 2 == 0)
    {
        throw a;
    }

}

// Helper function 2
// object type function
struct Class2
{
    void operator() (int a)
    {
        cout << a * 3 << " ";
        if ( a % 2 == 0)
        {
            throw a;

        }
    }
} ob1;

int main()
{

    // Initializing array
    int arr[5] = { 1, 5, 2, 4, 3 };

    cout << "Using Array" << endl;

    // Printing Exception using for_each
    // using function
    try
    {
        for_each(arr, arr + 5, printx2);
    }
    catch(int i)
    {
        cout << "\nThe Exception element is : " << i ;
    }
    cout << endl;

    // Printing Exception using for_each
    // using object function
    try
    {
        for_each(arr, arr + 5, ob1);
    }
    catch(int i)
    {
        cout << "\nThe Exception element is : " << i ;
    }

    // Initializing vector
    vector<int> arr1 = { 1, 3, 6, 5, 1 };

    cout << "\nUsing Vector" << endl;

    // Printing Exception using for_each
    // using function
    try
    {
        for_each(arr1.begin(), arr1.end(), printx2);
    }
    catch(int i)
    {
        cout << "\nThe Exception element is : " << i ;
    }
    cout << endl;

    // printing Exception using for_each
    // using object function
    try
    {
        for_each(arr1.begin(), arr1.end(), ob1);
    }
    catch(int i)
    {
        cout << "\nThe Exception element is : " << i ;
    }
}
```

**Output**

```cpp
Using Array
2 10 4 
The Exception element is : 2
3 15 6 
The Exception element is : 2
Using Vector
2 6 12 
The Exception element is : 6
3 9 18 
The Exception element is : 6
```

**使用 Lambdas:**

随着 lambda 函数的引入，这可以很容易地用来将整个事情内联起来，这对于寻求使用函数式编程的人来说是非常紧凑和有用的。

## C++

```cpp
#include <bits/stdc++.h>
#include <iostream>
using namespace std;

int main()
{

    vector<int> vec{ 1, 2, 3, 4, 5 };

    // this increases all the values in the vector by 1;
    for_each(vec.begin(), vec.end(), [](int& a) { a++ ; });

    // this prints all the values in the vector;
    for_each(vec.begin(), vec.end(),
             [](int a) { cout << a << " " << endl; });

    return 0;
}
```

**Output**

```cpp
2 
3 
4 
5 
6 
```

本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。