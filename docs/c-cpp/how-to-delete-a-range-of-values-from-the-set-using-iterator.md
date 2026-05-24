# 如何使用迭代器

从集合中删除一系列值

> 原文:[https://www . geeksforgeeks . org/如何使用迭代器从集合中删除值范围/](https://www.geeksforgeeks.org/how-to-delete-a-range-of-values-from-the-set-using-iterator/)

给定一个[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)，任务是使用迭代器从这个集合中删除一系列值。

**示例:**

```cpp
Input: set = [10 20 30 40 50 60 70 80 90],
              start_iterator = 3,
              end_iterator = 8
Output: 10 20 80 90

Input: set = [1 2 3 4 5]
              start_iterator = 1,
              end_iterator = 3
Output: 3 4 5

```

**方法:**在该方法中，从集合中删除一系列元素。这在两个[迭代器](https://www.geeksforgeeks.org/iterators-c-stl/)的帮助下完成。第一个迭代器指向范围的开始元素，第二个迭代器指向范围的最后一个元素。第一个迭代器是*独占*，而最后一个迭代器是*包含*，这意味着最后一个迭代器指向的元素也会被删除。

**语法:**

```cpp
iterator erase (const_iterator startPositionIterator_exclusive, 
                const_iterator endingPositionIterator_inclusive);

```

下面是上述方法的实现:

**程序:**

```cpp
// C++ program to delete an element
// of a Set by passing its value

#include <iostream>
#include <set>
using namespace std;

// Function to print the set
void printSet(set<int> myset)
{

    // Get the iterator
    set<int>::iterator it;

    // printing all the elements of the set
    for (it = myset.begin(); it != myset.end(); ++ it)
        cout << ' ' << *it;
    cout << '\n';
}

// Function to delete the element of set
void deleteRange(set<int> myset)
{

    // printing all the elements of the set
    cout << "\nSet originally: ";
    printSet(myset);

    // Get the starting Iterator at 3rd element
    set<int>::iterator start_itr = myset.begin();
    start_itr++ ;
    start_itr++ ;

    // Get the ending Iterator at 2nd last element
    set<int>::iterator end_itr = myset.end();
    end_itr--;
    end_itr--;

    // Erase the elements in the range
    // of the iterators passed as the parameter
    myset.erase(start_itr, end_itr);

    // printing all the elements of the set
    cout << "Set after deletion of range"
         << " from 3rd till 2nd last: ";
    printSet(myset);
}

// Driver code
int main()
{
    set<int> myset;

    // Get the set
    for (int i = 1; i < 10; i++)
        myset.insert(i * 10);

    // Delete an element from the Set
    deleteRange(myset);

    return 0;
}
```

**Output:**

```cpp
Set originally:  10 20 30 40 50 60 70 80 90
Set after deletion of range from 3rd till 2nd last:  10 20 80 90

```