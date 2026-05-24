# 如何在 C++ 中创建自定义类的无序 _ 映射？

> 原文:[https://www . geesforgeks . org/如何创建无序的用户定义类在 cpp 中的映射/](https://www.geeksforgeeks.org/how-to-create-an-unordered_map-of-user-defined-class-in-cpp/)

[无序 _ 映射](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)用于实现哈希表。它存储键值对。对于每个键，计算一个散列函数，并将值存储在该散列条目中。标准数据类型(int、char、string，..)是预定义的。如何使用我们自己的数据类型来实现哈希表？
无序映射允许第三个参数，用于指定我们自己的散列函数。

```cpp
// Create an unordered_map with given KeyType, 
// ValueType and hash function defined by 
// MyHashType
unordered_map<KeyType, ValueType, MyHashType> um;
```

这里 MyHashFunction 是必须包含一个**运算符函数()**的类或结构。
我们还必须在自己的类中实现**运算符==** ，用于处理[碰撞](https://www.geeksforgeeks.org/hashing-set-2-separate-chaining/)。
下面是一个示例代码，其中 Person 类的对象被用作键。我们定义了自己的散列函数，它使用名字和姓氏的长度之和作为哈希表中的关键字。请注意，此代码的目的只是演示如何使用简单的代码，长度总和作为哈希函数可能不是一个好主意。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of unordered_map
// for user defined data types.
#include <bits/stdc++.h>
using namespace std;

// Objects of this class are used as key in hash
// table. This class must implement operator ==()
// to handle collisions.
struct Person {
    string first, last;  // First and last names

    Person(string f, string l)
    {
        first = f;
        last = l;
    }

    // Match both first and last names in case
    // of collisions.
    bool operator==(const Person& p) const
    {
        return first == p.first && last == p.last;
    }
};

class MyHashFunction {
public:

    // Use sum of lengths of first and last names
    // as hash function.
    size_t operator()(const Person& p) const
    {
        return p.first.length() + p.last.length();
    }
};

// Driver code
int main()
{
    unordered_map<Person, int, MyHashFunction> um;
    Person p1("kartik", "kapoor");
    Person p2("Ram", "Singh");
    Person p3("Laxman", "Prasad");

    um[p1] = 100;
    um[p2] = 200;
    um[p3] = 100;

    for (auto e : um) {
        cout << "[" << e.first.first << ", "
             << e.first.last
             << "] = > " << e.second << '\n';
    }

    return 0;
}
```

**Output:** 

```cpp
[Laxman, Prasad] = > 100
[kartik, kapoor] = > 100
[Ram, Singh] = > 200
```

另一个例子是预定义散列类的预定义运算符函数构成我们的整体散列。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of unordered_map
// for user defined data types.
#include <bits/stdc++.h>
using namespace std;

struct Person {
    string first, last;

    Person(string f, string l)
    {
        first = f;
        last = l;
    }

    bool operator==(const Person& p) const
    {
        return first == p.first && last == p.last;
    }
};

class MyHashFunction {
public:

    // We use predefined hash functions of strings
    // and define our hash function as XOR of the
    // hash values.
    size_t operator()(const Person& p) const
    {
        return (hash<string>()(p.first)) ^
               (hash<string>()(p.last));
    }
};

// Driver code
int main()
{
    unordered_map<Person, int, MyHashFunction> um;
    Person p1("kartik", "kapoor");
    Person p2("Ram", "Singh");
    Person p3("Laxman", "Prasad");

    um[p1] = 100;
    um[p2] = 200;
    um[p3] = 100;

    for (auto e : um) {
        cout << "[" << e.first.first << ", "
             << e.first.last
             << "] = > " << e.second << '\n';
    }

    return 0;
}
```

**Output:** 

```cpp
[Laxman, Prasad] = > 100
[kartik, kapoor] = > 100
[Ram, Singh] = > 200
```