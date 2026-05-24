# c++ 中()处的无序 _ map

> 原文:[https://www.geeksforgeeks.org/unordered_map-at-cpp/](https://www.geeksforgeeks.org/unordered_map-at-cpp/)

**先决条件:**[STL 中的无序映射](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)
**无序 _ 映射:**无序 _ 映射是存储键值和映射值组合而成的元素的关联容器。键值用于唯一标识元素，映射值是与键相关联的内容。键和值都可以是预定义或用户定义的任何类型。
**无序 _map :: at():** 这个函数在 C++ 中**无序 _map** 返回对以元素为键 k 的值的引用。

**语法:**

```cpp
unordered_map.at(k);
Parameter:
It is the key value of the element whose mapped value we want to access.
Return type :
A reference to the mapped value of the element with a key value equivalent
```

**注意:**如果键不存在，该方法会给出**运行时**错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// std :: unordered_map :: at()
#include<iostream>
#include<string>
#include<unordered_map>

using namespace std;

int main()
{
    unordered_map<string,int> mp = {
                            {"first",1},
                            {"second",2},
                            {"third",3},
                            {"fourth",4}
    };

    // returns the reference i.e. the mapped
    // value with the key 'second'
    cout<<"Value of key mp['second'] = "
        <<mp.at("second")<<endl;

    try
    {
        mp.at();
    }

    catch(const out_of_range &e)
    {
        cerr << "Exception at " << e.what() << endl;
    }

    return 0;
}
```

**输出:**

```cpp
Value of key mp['second'] = 2
Exception at _Map_base::at
```

**实际应用:** std :: unordered_map :: at()函数可以用来访问映射的值，从而可以编辑、更新等。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// application of this function
// Program to correct the marks
// given in different subjects
#include<iostream>
#include<string>
#include<unordered_map>

using namespace std;

// driver code
int main()
{
    // marks in different subjects
    unordered_map<string,int> my_marks = {
                    {"Maths", 90},
                    {"Physics", 87},
                    {"Chemistry", 98},
                    {"Computer Application", 94}
                    };

        my_marks.at("Physics") = 97;
        my_marks.at("Maths") += 10;
        my_marks.at("Computer Application") += 6;

        for (auto& i: my_marks)
        {
            cout<<i.first<<": "<<i.second<<endl;
        }

    return 0;
}
```

**输出:**

```cpp
Computer Application: 100
Chemistry: 98
Physics: 97
Maths: 100
```

**在()的无序 _map 与无序 _map 运算符()有何不同**

*   at()和运算符[]都用于引用给定 ***位置*** 处存在的元素，唯一的区别是，at()抛出超范围异常，而运算符[]显示**未定义的行为**，即如果运算符[]用于查找键对应的值，并且如果键不存在于无序映射中，它将首先将键插入映射中，然后为该键分配默认值“0”。。