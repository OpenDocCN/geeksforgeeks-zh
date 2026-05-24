# C++ STL 中的 `unordered_multiset::hash_function()` 函数

> 原文: [https://www.geeksforgeeks.org/unordered_multiset-hash_function-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_multiset-hash_function-function-in-c-stl/)

`unordered_multiset::hash_function()` 是 C++ STL 中的一个内置函数，用来获取哈希函数。这个散列函数是一个一元函数，只接受一个参数，并根据它返回一个 `size_t` 类型的唯一值。

## 语法

```cpp
*unordered_multiset_name*.hash_function()
```

## 参数

函数不接受任何参数。

## 返回值

函数返回哈希函数。

下面的程序说明了 `unordered_multiset::hash_function()` 函数：

## 程序 1

```cpp
// CPP program to illustrate the
// unordered_multiset::hash_function() function

#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{

unordered_multiset<string> sampleSet = { "geeks1", "geeks1", "for", "geeks2" };

// use of hash_function
    unordered_multiset<string>::hasher fn = sampleSet.hash_function();

cout << fn("geeks") << endl;

for (auto it = sampleSet.begin(); it != sampleSet.end(); it++) {
        cout << *it << " ";
    }
    cout << endl;

return 0;
}
```

**Output:**

```cpp

geeks2 for geeks1 geeks1

```

## 程序 2

```cpp
// CPP program to illustrate the
// unordered_multiset::hash_function () function

#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{

unordered_multiset<string> sampleSet;

// use of hash_function
    unordered_multiset<string>::hasher fn = sampleSet.hash_function();

cout << fn("geeksforgeeks") << endl;

return 0;
}
```

**Output:**

```cpp

```