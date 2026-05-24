# c++ STL 中的无序 _ 多映射 hash_function()

> 原文:[https://www . geesforgeks . org/unordered _ multimap-hash _ function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-hash_function-in-c-stl/)

**无序 _ 多 map::hash_function()** 是 C++ STL 中的一个内置函数，用来获取 hash 函数。这个散列函数是一元函数，只接受一个参数，并基于它返回类型为 *size_t* 的唯一值。

**语法**:

```cpp
*unordered_multimap_name*.hash_function()
```

**参数**:函数不接受任何参数。

**返回值**:函数返回哈希函数。

下面的程序说明了*无序 _ 多映射::哈希 _ 函数()*函数:

**程序 1** :

```cpp
// C++ program to illustrate the
// unordered_multimap::hash_function()
#include <iostream>
#include <unordered_map>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<string, string> sample;

    // inserts key and elements
    sample.insert({ "gopal", "dave" });
    sample.insert({ "gopal", "dave" });
    sample.insert({ "gopal", "dave" });
    sample.insert({ "geeks", "geeks" });

    // use of hash_function
    unordered_multimap<string, string>::hasher fn
                                      = sample.hash_function();

    cout << fn("geeks") << endl;

    // print the key and elements

    cout << "Key and Elements: ";
    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "{" << it->first << ":"
             << it->second << "}, ";
    }
    return 0;
}
```

**Output:**

```cpp
15276750567035005396
Key and Elements: {geeks:geeks}, {gopal:dave}, {gopal:dave}, {gopal:dave},

```

**程序 2** :

```cpp
// C++ program to illustrate the
// unordered_multimap::hash_function()
#include <iostream>
#include <unordered_map>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<string, string> sample;

    // insertion of key and elements
    sample.insert({ "gopal", "dave" });
    sample.insert({ "geeks", "geeks" });

    // use of hash_function
    unordered_multimap<string, string>::hasher fn
                                      = sample.hash_function();

    cout << fn("geeksforgeeks") << endl;

    // print the key and elements
    cout << "Key and Elements: ";
    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "{" << it->first << ":"
             << it->second << "}, ";
    }
    return 0;
}
```

**Output:**

```cpp
5146686323530302118
Key and Elements: {geeks:geeks}, {gopal:dave},

```