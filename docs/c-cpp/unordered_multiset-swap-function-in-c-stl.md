# c++ STL 中的无序 _ 多集交换()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-swap-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-swap-function-in-c-stl/)

**无序 _ 多集::交换()**是 C++ STL 中的一个内置函数，它交换两个无序 _ 多集
容器的内容。

**注**:两个容器的元素类型应该相同。容器的尺寸可能不同。

**语法:**

```cpp
unordered_multiset1.swap(unordered_multiset2);
```

**参数:**该函数只接受一个强制参数，即无序 _ 多集 2，无序 _ 多集 1 的交换将通过该参数完成。

**返回值:**不返回值。

下面的程序说明了上述功能。

**程序 1:**

## C++

```cpp
// C++ program to illustrate
// unordered_multiset::swap()
#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

// Function to display the contents of multiset s.
void display(unordered_multiset<int> s)
{
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it<<" ";
    cout<<"\n";   
}

int main()
{
    // Declaration
    unordered_multiset<int> s1, s2;

    // initializing both multisets(sizes are different)
    s1 = { 1, 2, 3, 4 };
    s2 = { 10, 20, 30, 40, 50 };

    // displaying initial values
    cout << "Initial values of s1 are: \n";
    display(s1);
    cout << endl;

    cout << "Initial values of s2 are: \n";
    display(s2);
    cout << endl;

    // swapping the values
    s1.swap(s2);

    // display final values
    cout << "Final values of s1 are: \n";
    display(s1);
    cout << endl;

    cout << "Final values of s2 are: \n";
    display(s2);

    return 0;
}
```

**Output:** 

```cpp
Initial values of s1 are: 
4 3 2 1 

Initial values of s2 are: 
50 40 30 20 10 

Final values of s1 are: 
50 40 30 20 10 

Final values of s2 are: 
4 3 2 1
```

**程序 2:**

## C++

```cpp
// C++ program to illustrate
// unordered_multiset::swap()
#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

// Function to display the contents of multiset s
void display(unordered_multiset<string> s)
{
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";
    cout<<endl;
}

int main()
{
    // Declaration
    unordered_multiset<string> s1, s2;

    // Initializing both multisets(sizes are different)
    s1 = { "Geeks", "for", "Geeks" };
    s2 = { "Computer", "Science", "Portal", "for", "Geeks" };

    // Displaying initial values
    cout << "Initial values of s1 are: \n";
    display(s1);
    cout << endl;

    cout << "Initial values of s2 are: \n";
    display(s2);
    cout << endl;

    // Swapping
    s1.swap(s2);

    // Display final values
    cout << "Final values of s1 are: \n";
    display(s1);
    cout << endl;

    cout << "Final values of s2 are: \n";
    display(s2);

    return 0;
}
```

**Output:** 

```cpp
Initial values of s1 are: 
for Geeks Geeks 

Initial values of s2 are: 
Geeks for Portal Science Computer 

Final values of s1 are: 
Geeks for Portal Science Computer 

Final values of s2 are: 
for Geeks Geeks
```