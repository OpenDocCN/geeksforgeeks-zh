# c++ STL 中的无序 _ 多集 key_eq()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-key _ eq-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-key_eq-function-in-c-stl/)

**无序 _ 多集::key_eq()** 是 C++ STL 中的内置函数，根据比较结果返回布尔值。它依赖于无序多集容器使用的键等价比较谓词。键等价比较是一个谓词，它接受两个参数并返回一个布尔值，指示它们是否被认为是等价的。如果它们相等，则返回真，否则返回假。集装箱在施工中采用，与对比中使用的 *(==)* 操作员相似。

**语法**:

```cpp
*unordered_multiset_name*.key_eq()(args1, args2)
```

**参数**:该函数接受两个强制参数*参数 1* 和*参数 2* ，在这两个参数之间进行比较。数据类型与无序多集的数据类型相同。

**返回值**:该函数返回一个布尔值。

以下程序说明了*无序 _ 多集::key_eq()* 功能:

**程序 1** :

```cpp
// CPP program to illustrate the
// unordered_multiset::key_eq() function

#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_multiset<string> sampleSet;

    bool answer = sampleSet.key_eq()("GEEKS", "geeks");

    // checks if both are same
    if (answer)
        cout << "GEEKS and geeks are treated similarly in the container\n";
    else
        cout << "GEEKS and geeks are treated dissimilarly in the container\n";

    return 0;
}
```

**Output:**

```cpp
GEEKS and geeks are treated dissimilarly in the container

```

**程序 2** :

```cpp
// CPP program to illustrate the
// unordered_multiset::key_eq() function

#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_multiset<int> sampleSet;

    bool answer = sampleSet.key_eq()(100, 200);

    // check
    if (answer)
        cout << "100 and 200 are treated similarly in the container\n";
    else
        cout << "100 and 200 are treated dissimilarly in the container\n";

    answer = sampleSet.key_eq()(100, 100);
    if (answer)
        cout << "100 and 100 are treated similarly in the container\n";
    else
        cout << "100 and 100 are treated dissimilarly in the container\n";

    return 0;
}
```

**Output:**

```cpp
100 and 200 are treated dissimilarly in the container
100 and 100 are treated similarly in the container

```