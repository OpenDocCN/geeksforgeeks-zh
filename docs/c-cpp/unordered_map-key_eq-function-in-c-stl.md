# c++ STL 中的无序 _ 映射键 _eq()函数

> 原文:[https://www . geesforgeks . org/unordered _ map-key _ eq-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_map-key_eq-function-in-c-stl/)

**[无序 _ 映射](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/):key _ eq()**是 C++ STL 中的内置函数，根据比较结果返回一个布尔值。这取决于无序映射容器使用的键等价比较谓词。键等价比较是一个谓词，它接受两个参数并返回一个布尔值，指示它们是否被认为是等价的。如果它们相等，则返回真，否则返回假。容器在构造时采用它，它类似于比较中使用的(==)运算符。

**语法**

```cpp
unordered_map_name.key_eq()(args1, args2)

```

**参数:**函数接受两个强制参数 args1 和 args2，在这两个参数之间进行比较。数据类型与无序映射的数据类型相同。

**返回值:**函数返回一个布尔值。

下面的程序说明了无序的 map::key_eq()函数。

**例 1:**

```cpp
// CPP program to illustrate the
// unordered_map::key_eq() function

#include <bits/stdc++.h>

using namespace std;

int main()
{
    // Declaring unordered_map
    unordered_map<string, string> sample;

    // check details
    bool answer
        = sample.key_eq()("GEEKS", "geeks");

    // checks if both are same
    if (answer)
        cout << "GEEKS and geeks are treated"
             << " similarly in the container\n";
    else
        cout << "GEEKS and geeks are treated"
             << " dissimilarly in the container\n";

    return 0;
}
```

**Output:**

```cpp
GEEKS and geeks are treated dissimilarly in the container

```

**例 2:**

```cpp
// CPP program to illustrate the
// unordered_map::key_eq() function

#include <bits/stdc++.h>

using namespace std;

int main()
{

    unordered_map<int, int> sample;

    bool answer = sample.key_eq()(100, 200);

    // check
    if (answer)
        cout << "100 and 200 are treated "
             << "similarly in the container\n";
    else
        cout << "100 and 200 are treated"
             << " dissimilarly in the container\n";

    answer = sample.key_eq()(100, 100);
    if (answer)
        cout << "100 and 100 are treated "
             << "similarly in the container\n";
    else
        cout << "100 and 100 are treated "
             << "dissimilarly in the container\n";

    return 0;
}
```

**Output:**

```cpp
100 and 200 are treated dissimilarly in the container
100 and 100 are treated similarly in the container

```