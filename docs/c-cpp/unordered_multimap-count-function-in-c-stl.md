# c++ STL 中无序 _ 多 map count()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-count-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-count-function-in-c-stl/)

**unordered _ multimap::count()**是 C++ STL 中的一个内置函数，它返回容器中其键等于参数中传递的键的元素数。

**语法:**

```cpp
u*nordered_multimap_name*.count(key)
```

**参数:**该函数接受单个强制参数*键*，该参数指定要返回无序多映射容器中其计数的键。

**返回值:**返回一个无符号整数类型，表示*键*在容器中出现的次数。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::count()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample;

    // inserts key and element
    sample.insert({ 10, 100 });
    sample.insert({ 10, 100 });
    sample.insert({ 20, 200 });
    sample.insert({ 30, 300 });
    sample.insert({ 30, 150 });

    cout << "10 occurs " << sample.count(10) 
         << " times";

    cout << "\n20 occurs " << sample.count(20) 
         << " times";

    cout << "\n13 occurs " << sample.count(13) 
         << " times";

    cout << "\n30 occurs " << sample.count(30) 
         << " times";

    return 0;
}
```

**Output:**

```cpp
10 occurs 2 times
20 occurs 1 times
13 occurs 0 times
30 occurs 2 times

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::count()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<char, char> sample;

    // inserts key and element
    sample.insert({ 'a', 'b' });
    sample.insert({ 'a', 'b' });
    sample.insert({ 'b', 'c' });
    sample.insert({ 'r', 'a' });
    sample.insert({ 'r', 'b' });

    cout << "a occurs " << sample.count('a') 
         << " times";

    cout << "\nb occurs " << sample.count('b') 
         << " times";

    cout << "\nz occurs " << sample.count('z') 
         << " times";

    cout << "\nr occurs " << sample.count('r') 
         << " times";

    return 0;
}
```

**Output:**

```cpp
a occurs 2 times
b occurs 1 times
z occurs 0 times
r occurs 2 times

```