# c++ STL 中的无序 _map end()函数

> 原文:[https://www . geesforgeks . org/unordered _ map-end-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_map-end-function-in-c-stl/)

**无序 _map::end()** 是 C++ STL 中的内置函数，它返回一个迭代器，指向无序 _map 容器中容器中最后一个元素的位置**。在无序映射对象中，不能保证哪个特定元素被认为是它的第一个元素。但是容器中的所有元素都被覆盖了，因为范围从它的开始到它的结束一直到无效。**

**语法:**

```cpp
iterator unordered_map_name.end(n)
```

**参数:**该函数接受一个参数 **n** ，该参数是一个可选参数，用于指定铲斗编号。如果设置了，迭代器将检索指向桶的结束元素的指针，否则，它将指向容器的结束元素。

**返回值:**该函数返回一个迭代器到容器末尾之后的元素。

下面的程序说明了上述功能:

**程序 1:**

```cpp
// CPP program to demonstrate the
// unordered_map::end() function
// returning all the elements of the multimap
#include <iostream>
#include <string>
#include <unordered_map>
using namespace std;

int main()
{
    unordered_map<string, int> marks;

    // Declaring the elements of the multimap
    marks = { { "Rohit", 64 }, { "Aman", 37 }, { "Ayush", 96 } };

    // Printing all the elements of the multimap
    cout << "marks bucket contains : " << endl;
    for (int i = 0; i < marks.bucket_count(); ++ i) {

        cout << "bucket #" << i << " contains:";

        for (auto iter = marks.begin(i); iter != marks.end(i); ++ iter) {
            cout << "(" << iter->first << ", " << iter->second << "), ";
        }

        cout << endl;
    }
    return 0;
}
```

**Output:**

```cpp
marks bucket contains : 
bucket #0 contains:
bucket #1 contains:
bucket #2 contains:
bucket #3 contains:(Aman, 37), (Rohit, 64), 
bucket #4 contains:(Ayush, 96),

```

**程序 2** :

```cpp
// CPP program to demonstrate the
// unordered_map::end() function
// returning the elements along
// with their bucket number
#include <iostream>
#include <string>
#include <unordered_map>

using namespace std;

int main()
{
    unordered_map<string, int> marks;

    // Declaring the elements of the multimap
    marks = { { "Rohit", 64 }, { "Aman", 37 }, { "Ayush", 96 } };

    // Printing all the elements of the multimap
    for (auto iter = marks.begin(); iter != marks.end(); ++ iter) {

        cout << "Marks of " << iter->first << " is "
             << iter->second << " and his bucket number is "
             << marks.bucket(iter->first) << endl;
    }

    return 0;
}
```

**Output:**

```cpp
Marks of Ayush is 96 and his bucket number is 4
Marks of Aman is 37 and his bucket number is 3
Marks of Rohit is 64 and his bucket number is 3

```