# c++ STL 中的无序 _ 多集最大 _ 加载 _ 因子()

> 原文:[https://www . geesforgeks . org/无序 _ 多集-max_load_factor-in-c-stl/](https://www.geeksforgeeks.org/unordered_multiset-max_load_factor-in-c-stl/)

无序多集::max_load_factor()是 C++ STL 中的内置函数，返回无序多集容器的最大[加载因子](https://www.geeksforgeeks.org/unordered_multiset-load_factor-function-in-c-stl/)。该功能还提供了设置最大[负载系数](https://www.geeksforgeeks.org/unordered_multiset-load_factor-function-in-c-stl/)的选项。

**语法**(返回最大负载系数):

```cpp
unordered_multiset_name.max_load_factor()

```

**参数:**函数不接受任何参数。

**返回值:**返回表示集装箱最大装载系数的整数值。

以下程序说明了无序多集::max_load_factor()函数:

**程序 1** :

```cpp
// C++ program to illustrate
// unordered_multiset::max_load_factor()
#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{
    // declaration
    unordered_multiset<char> s1;
    s1 = { 'a', 'b', 'c', 'd' };

    // displaying initial parameters
    cout << "Current parameters are :\n";
    cout << "max_load_factor= " << s1.max_load_factor() << endl;
    cout << "load_factor= " << s1.load_factor() << endl;
    cout << "size of s1= " << s1.size() << endl;
    cout << "bucket_count= " << s1.bucket_count() << endl;

    return 0;
}
```

**Output:**

```cpp
Current parameters are :
max_load_factor= 1
load_factor= 0.571429
size of s1= 4
bucket_count= 7

```

**程序 2** :

```cpp
// c++ program to illustrate
// unordered_multiset::max_load_factor()
#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{
    // declaration
    unordered_multiset<char> s1;
    s1 = { 'a', 'b', 'c', 'd' };

    // displaying initial parameters
    cout << "Current parameters are :\n";
    cout << "max_load_factor= " << s1.max_load_factor() << endl;
    cout << "load_factor= " << s1.load_factor() << endl;
    cout << "size of s1= " << s1.size() << endl;
    cout << "bucket_count= " << s1.bucket_count() << endl;

    // changing max_load_factor
    s1.max_load_factor(0.5);
    cout << endl;

    // displaying final parameters
    cout << "Final parameters are :\n";
    cout << "max_load_factor= " << s1.max_load_factor() << endl;
    cout << "load_factor= " << s1.load_factor() << endl;
    cout << "size of s1= " << s1.size() << endl;
    cout << "bucket_count= " << s1.bucket_count() << endl;

    return 0;
}
```

**Output:**

```cpp
Current parameters are :
max_load_factor= 1
load_factor= 0.571429
size of s1= 4
bucket_count= 7

Final parameters are :
max_load_factor= 0.5
load_factor= 0.235294
size of s1= 4
bucket_count= 17

```