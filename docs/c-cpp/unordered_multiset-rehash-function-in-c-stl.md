# c++ STL 中的无序 _ 多集重散列()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-rehash-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-rehash-function-in-c-stl/)

**无序 _ 多集::重散列()**是 C++ STL 中的一个内置函数，它将容器中的桶数设置为 N 或更多。如果 N 大于容器中当前的桶数(桶计数)，则强制重新散列。
新的桶计数可以等于或大于 n。如果 n 小于容器中当前的桶数([桶计数](https://www.geeksforgeeks.org/unordered_multiset-bucket_count-function-in-c-stl/)，该功能可能对桶计数没有影响，并且可能不会强制重新散列。

重新散列是哈希表的重建:容器中的所有元素根据它们的哈希值重新排列成新的桶集。这可能会改变容器内元素的迭代顺序，尽管保留了具有等效键的元素的相对顺序。每当容器的[负载系数](https://www.geeksforgeeks.org/unordered_multiset-load_factor-function-in-c-stl/)在一次操作中将要超过其最大负载系数时，容器会自动执行重新灰化。通过调用 rehash 在哈希表中保留一定数量的最小桶，我们避免了容器扩展可能导致的多次重散列。

**语法:**

```cpp
unordered_multset_name.rehash(N);
```

**参数:**该函数只接受一个参数，如下所示:

*   **计数**:是新桶数。

**返回值:**无(空型函数)

下面的程序说明了上述方法:

**程序 1:**

## C++

```cpp
// C++ program to illustrate
// unordered_multiset::rehash()
#include <iostream>
#include <unordered_set>
using namespace std;

// function to display values in multiset
void display(unordered_multiset<int> s)
{
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << endl;
}

int main()
{
    // declaration
    unordered_multiset<int> s1;

    // inserting initial values
    s1.insert(1);
    s1.insert(2);
    s1.insert(3);

    // displaying Initial values
    cout << "Initial values are:\n";
    display(s1);
    cout << endl;

    // displaying initial parameters
    cout << "initial parameters are: \n";
    cout << "bucketcount() = " << s1.bucket_count() << endl;
    cout << "load factor = " << s1.load_factor() << endl;
    cout << "Max_load_factor = " << s1.max_load_factor() << endl;
    cout << endl;

    // performing rehash
    s1.rehash(200);

    // displaying final parameters
    cout << "final parameters are: \n";
    cout << "bucketcount() = " << s1.bucket_count() << endl;
    cout << "load factor = " << s1.load_factor() << endl;
    cout << "Max_load_factor = " << s1.max_load_factor() << endl;
    cout << endl;

    return 0;
}
```

**Output:** 

```cpp
Initial values are:
3
1
2

initial parameters are: 
bucketcount() = 7
load factor = 0.428571
Max_load_factor = 1

final parameters are: 
bucketcount() = 211
load factor = 0.014218
Max_load_factor = 1
```

**程序 2:**

## C++

```cpp
// C++ program to illustrate
// unordered_multiset::rehash()
#include <iostream>
#include <unordered_set>
using namespace std;

// function to display values in multiset
void display(unordered_multiset<char> s)
{
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << endl;
}
int main()
{
    // declaration
    unordered_multiset<char> s1;

    // inserting initial values
    s1.insert('a');
    s1.insert('b');
    s1.insert('c');

    // displaying Initial values
    cout << "Initial values are:\n";
    display(s1);
    cout << endl;

    // displaying initial parameters
    cout << "initial parameters are: \n";
    cout << "bucketcount() = " << s1.bucket_count() << endl;
    cout << "load factor = " << s1.load_factor() << endl;
    cout << "Max_load_factor = " << s1.max_load_factor() << endl;
    cout << endl;

    // performing rehash
    s1.rehash(200);

    // displaying final parameters
    cout << "final parameters are: \n";
    cout << "bucketcount() = " << s1.bucket_count() << endl;
    cout << "load factor = " << s1.load_factor() << endl;
    cout << "Max_load_factor = " << s1.max_load_factor() << endl;
    cout << endl;

    return 0;
}
```

**Output:** 

```cpp
Initial values are:
c
a
b

initial parameters are: 
bucketcount() = 7
load factor = 0.428571
Max_load_factor = 1

final parameters are: 
bucketcount() = 211
load factor = 0.014218
Max_load_factor = 1
```