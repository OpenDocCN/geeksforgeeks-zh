# c++ STL 中的无序 _ 映射 hash_function()函数

> 原文:[https://www . geesforgeks . org/unordered _ map-hash _ function-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_map-hash_function-function-in-c-stl/)

**无序 _ 映射::hash_function()** 是 C++ STL 中的一个内置函数，用来获取 hash 函数。这个散列函数是一个一元函数，只接受一个参数，并根据它返回一个 size_t 类型的唯一值。

**语法:**

```cpp
unordered_map_name.hash_function()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回散列函数。

**时间复杂度:**该函数的时间复杂度为常数 O(1)。

下面的程序说明了无序 _map::hash_function()函数。

**例 1**

```cpp
// C++ program to illustrate the
// unordered_map::hash_function()

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_map<string, string> sample;

    // inserts key and elements
    sample.insert({ "Ankit", "MNNIT" });
    sample.insert({ "Ram", "MNNIT" });
    sample.insert({ "Manoj", "Trichy" });
    sample.insert({ "geeks", "geeks" });

    // use of hash_function
    unordered_map<string, string>::hasher fn
        = sample.hash_function();

    cout << fn("geeks") << endl;

    // print the key and elements

    cout << "Key and Elements: ";
    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "\n{" << it->first << ":"
             << it->second << "}, ";
    }
    return 0;
}
```

**Output:**

```cpp
15276750567035005396
Key and Elements: 
{geeks:geeks}, 
{Manoj:Trichy}, 
{Ankit:MNNIT}, 
{Ram:MNNIT},

```

**例 2**

```cpp
// C++ program to illustrate the
// unordered_map::hash_function()

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_map<int, int> sample;

    // inserts key and elements
    sample.insert({ 1, 5 });
    sample.insert({ 2, 6 });
    sample.insert({ 3, 6 });
    sample.insert({ 4, 7 });

    // use of hash_function
    unordered_map<int, int>::hasher fn
        = sample.hash_function();

    cout << fn(4) << endl;

    // print the key and elements

    cout << "Key and Elements: ";
    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "\n{" << it->first << ":"
             << it->second << "}, ";
    }
    return 0;
}
```

**Output:**

```cpp
4
Key and Elements: 
{4:7}, 
{3:6}, 
{1:5}, 
{2:6},

```