# c++ STL 中无序 _ 多映射桶()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-bucket-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-bucket-function-in-c-stl/)

**unordered _ multimap::bucket()**是 C++ STL 中的一个内置函数，它返回给定键所在的存储桶号。铲斗大小从 0 到*铲斗 _ 计数-1 不等。*

**语法:**

```cpp
*unordered_multimap_name*.bucket(key)
```

**参数:**该功能接受单个强制参数*键*，该键指定要返回其桶号的键。

**返回值:**返回无符号整数类型，表示关键字所在的桶号。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::bucket() 
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
    sample.insert({ 15, 150 });

    // iterate for all elements and print its bucket number
    for (auto it = sample.begin(); 
                  it != sample.end(); it++) {
        cout << "The bucket number in which {" 
             << it->first << ", " 
             << it->second << "} is " 
             << sample.bucket(it->first) << endl;
    }
    return 0;
}
```

**Output:**

```cpp
The bucket number in which {15, 150} is 1
The bucket number in which {30, 300} is 2
The bucket number in which {20, 200} is 6
The bucket number in which {10, 100} is 3
The bucket number in which {10, 100} is 3

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::bucket() 
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
    sample.insert({ 'c', 'b' });

    // iterate for all elements and print its bucket number
    for (auto it = sample.begin(); 
                    it != sample.end(); it++) {
        cout << "The bucket number in which {" 
             << it->first << ", "
             << it->second << "} is " 
             << sample.bucket(it->first) << endl;
    }
    return 0;
}
```

**Output:**

```cpp
The bucket number in which {c, b} is 1
The bucket number in which {r, a} is 2
The bucket number in which {b, c} is 0
The bucket number in which {a, b} is 6
The bucket number in which {a, b} is 6

```