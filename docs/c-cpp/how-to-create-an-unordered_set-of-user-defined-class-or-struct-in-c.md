# 如何在 C++ 中创建一个用户定义的类或结构的无序 _ 集合？

> 原文:[https://www . geesforgeks . org/如何创建一个无序的用户定义类或结构集合/](https://www.geeksforgeeks.org/how-to-create-an-unordered_set-of-user-defined-class-or-struct-in-c/)

[**无序集**](https://www.geeksforgeeks.org/unorderd_set-stl-uses/) 内部实现了一个哈希表来存储元素。默认情况下，我们只能存储预定义的类型，如 int、string、float 等。
如果我们想将用户定义类型的元素存储为结构，那么编译器会显示一个错误，因为在将元素存储到无序集之前，编译器会执行一些检查。当比较两个用户定义的类型时，编译器不能比较它们，因此会产生错误。
所以，为了在无序 _ 集合中存储一个结构，需要设计一些比较函数。由于无序 _ set store 也实现了哈希表来存储元素，因此我们还应该实现哈希函数来执行哈希相关的工作。
以下方法说明其实现。
**实现:**我们创建一个结构类型，并在该结构内部定义一个比较函数，用于比较两个结构类型对象。由于无序集在内部实现了散列函数，所以我们也应该为用户定义的类型对象实现散列函数。
**语法**存储用户定义的类型元素无序 _ 集合应遵循以下语法

```cpp
unordered_set(elementType, MyHashType) us;
// element type is user defined type and MyHashType is class implementing hash function
```

下面的代码解释了一下。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP implementation to use
// user-defined data type in
// structures
#include <bits/stdc++.h>
using namespace std;

// Structure definition
struct Test {

    int id;

    // This function is used by unordered_set to compare
    // elements of Test.
    bool operator==(const Test& t) const
    {
        return (this->id == t.id);
    }
};

// class for hash function
class MyHashFunction {
public:
    // id is returned as hash function
    size_t operator()(const Test& t) const
    {
        return t.id;
    }
};

// Driver method
int main()
{
    // put values in each
    // structure define below.
    Test t1 = { 110 }, t2 = { 102 },
         t3 = { 101 }, t4 = { 115 };

    // define a unordered_set having
    // structure as its elements.
    unordered_set<Test, MyHashFunction> us;

    // insert structure in unordered_set
    us.insert(t1);
    us.insert(t2);
    us.insert(t3);
    us.insert(t4);

    // printing the elements of unordered_set
    for (auto e : us) {
        cout << e.id << " ";
    }

    return 0;
}
```

**Output:** 

```cpp
115 101 110 102
```

**Output:** 

```cpp
115 101 110 102
```

下面是另一个例子，我们使用预定义的散列函数来生成我们定义的类的整体散列函数。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of unordered_set
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
        return (hash<string>()(p.first)) ^ (hash<string>()(p.last));
    }
};

// Driver code
int main()
{
    unordered_set<Person, MyHashFunction> us;
    Person p1("kartik", "kapoor");
    Person p2("Ram", "Singh");
    Person p3("Laxman", "Prasad");

    us.insert(p1);
    us.insert(p2);
    us.insert(p3);

    for (auto e : us) {
        cout << "[" << e.first << ", "
             << e.last << "]\n";
    }

    return 0;
}
```

**Output:** 

```cpp
[Laxman, Prasad]
[kartik, kapoor]
[Ram, Singh]
```