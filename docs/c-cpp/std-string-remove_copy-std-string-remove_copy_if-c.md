# std::string::remove_copy()，std::string::remove_copy_if()在 C++ 中

> 原文:[https://www . geesforgeks . org/STD-string-remove _ copy-STD-string-remove _ copy _ if-c/](https://www.geeksforgeeks.org/std-string-remove_copy-std-string-remove_copy_if-c/)

**remove_copy()**

它是算法库中定义的 c++ 中的一个 STL 函数。它将范围[第一个，最后一个]中的元素复制到从结果开始的范围，除了那些与给定元素比较相等的元素。

*   得到的范围比[第一个，最后一个]短，因为序列中匹配的元素一样多，这些元素被“移除”。
*   未被移除的元素的相对顺序被保留。
*   该函数使用运算符==将各个元素与给定值进行比较。

**功能模板**

```cpp
ResultIterator remove_copy(ForwardIterator first, ForwardIterator last, 
ResultIterator result ,const T& ele);

first, last :  Forward iterators to the initial and final positions
in a sequence. The range used is [first, last), which contains all the elements
between first and last, including the element pointed by first but not 
the element pointed by last.

result : Output iterator to the initial position of the range 
where the resulting sequence is stored. The pointed type shall support being 
assigned the value of an element in the range [first, last).

ele : element to be removed.

```

示例:

```cpp
Input : b d a f g h a k   given element is a
Output :b d f g h k _ _ 
Input : b k c s n m c l   given element is c
Output : b k s n m l _ _

'_' represent remove places
```

```cpp
// CPP code to demonstrate remove_copy()
#include <vector>
#include <algorithm>
#include <iostream>
using namespace std;

// Function to remove_copy from v1 result vector is v2
void removecopyDemo(vector <int> &v1)
{
    remove_copy(v1.begin(), v1.end(), v1.begin(), 3);
}

// Function to print content of vector
void print(vector<int>&v)
{
    int len = v.size();
    for (int i = 0; i < len; i++)
        cout << v[i] << " ";
    cout << endl;
}

// Driver code
int main()
{
    // vector 
    vector <int> v1, v2(10);

    // push data in vector 
    for(int i = 10; i <= 25; i++)
        v1.push_back(i % 6);

    cout << "elements of v1 before remove_copy: "<<endl;
    print(v1);

   removecopyDemo(v1);

   cout << "After removing element  3" <<endl;
    print(v1);

return 0;

}
```

**Output:**

```cpp
elements of v1 before remove_copy: 
4 5 0 1 2 3 4 5 0 1 2 3 4 5 0 1 
After removing element 3
4 5 0 1 2 4 5 0 1 2 4 5 0 1 0 1

```

复杂性:线性 O(n)

**移除 _ 复制 _ 如果**

它是算法库中定义的 c++ 中的一个 STL 函数。它将范围[第一个，最后一个]中的元素复制到从结果开始的范围，满足给定条件(如奇数、偶数、素数、非素数等)的元素除外。

*   将范围[第一个，最后一个]中的元素复制到从结果开始的范围，条件函数返回 true 的元素除外。
*   得到的范围比[第一个，最后一个]短，因为匹配的元素一样多，这些元素被“移除”。

**功能模板**

```cpp
ResultIterator remove_copy_if(ForwardIterator first, ForwardIterator last,
                                 ResultIterator result, UnaryPredicate pred);
pred :  Unary function that accepts an element in the range as
argument, and returns a value convertible to bool. The value returned indicates
 whether the element is to be removed (if true, it is removed).

```

示例:

```cpp
Input : 1 2 3 4 5 6 7 8 9 check if a number is prime and remove
Output :1 4 6 8 9 0 0 0 0

Input :1 2 3 4 5 6 7 8 9   check if a number is even and remove
Output :1 3 5 7 9 0 0 0 0

```

```cpp
// CPP code to demonstrate remove_copy_if()
#include <vector>
#include <algorithm>
#include <iostream>
using namespace std;

bool IsOdd(int i) { return ((i % 2) != 0); }

// Function to remove_copy from v1 result vector is v2
void remove_copy_ifDemo(vector <int> &v1, vector<int> &v2)
{
    remove_copy_if(v1.begin(), v1.end(), v2.begin(), IsOdd);
}

// Function to print content of vector
void print(vector<int>&v)
{
    int len = v.size();
    for (int i = 0; i < len; i++)
        cout << v[i] << " ";
    cout << endl;
}

// Driver code
int main()
{
    // declare vector v1, v2
    vector <int> v1, v2(10);

    // push data in vector 
    for(int i = 10; i <= 20; i++)
        v1.push_back(i);

    cout << "elements of v1 before remove_copy: ";
    print(v1);

remove_copy_ifDemo(v1,v2);

    cout << "elements of v1 after remove_copy: ";
    print(v1);

cout << "After removing Odd Numbers from v1"
            " copy result in vector v2" <<endl;
    print(v2);

return 0;

}
```

**Output:**

```cpp
elements of v1 before remove_copy: 10 11 12 13 14 15 16 17 18 19 20 
elements of v1 after remove_copy: 10 11 12 13 14 15 16 17 18 19 20 
After removing Odd Numbers from v1 copy result in vector v2
10 12 14 16 18 20 0 0 0 0

```

复杂性:线性 O(n)

[c++ STL 中的<算法>库列表](https://www.geeksforgeeks.org/algorithms-library-c-stl/)
[c++ 的所有 STL 文章](https://www.geeksforgeeks.org/tag/stl/)