# 结构或类的 STL 优先级队列

> 原文:[https://www . geesforgeks . org/STL-优先级-队列-针对结构或类/](https://www.geeksforgeeks.org/stl-priority-queue-for-structure-or-class/)

[STL priority_queue](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/) 是[堆数据结构](https://www.geeksforgeeks.org/heap-data-structure/)的实现。默认情况下，它是一个最大堆，我们可以很容易地将其用于原始数据类型。它有一些重要的应用可以在[这里](https://www.geeksforgeeks.org/applications-priority-queue/)找到

**先决条件:**[priority _ queue basic](https://www.geeksforgeeks.org/priority_queuepush-priority_queuepop-c-stl/)

在本文中，我们将看到如何将 priority_queue 用于自定义数据类型，如类或结构。
假设我们有一个名为 Person 的结构，它由两个变量组成**年龄**和**身高**T5，我们想把它存储在 priority_queue 中，那么一个简单的方法在这里不起作用。

下面是结构人声明的一个例子:

## C++

```cpp
struct Person{
int Age;
float Height;
}
```

在定义如下所示的优先级队列时，它会给我们带来错误，因为 priority_queue 不知道我们需要以什么顺序(最小或最大)排列对象。

## C++

```cpp
priority_queue<Person> pq;
```

为了纠正上面的错误，我们将使用[运算符重载](https://www.geeksforgeeks.org/operator-overloading-c/)来定义优先级。以便 priority_queue 可以决定如何存储结构对象。

下面给出了优先级队列的实现，其结构如下:

## C++

```cpp
// program in c++ to use priority_queue with structure

#include <iostream>
#include <queue>
using namespace std;
#define ROW 5
#define COL 2

struct Person {

    int age;

    float height;

    // this will used to initialize the variables
    // of the structure
    Person(int age, float height)
        : age(age), height(height)
    {
    }
};

// this is an structure which implements the
// operator overloading
struct CompareHeight {
    bool operator()(Person const& p1, Person const& p2)
    {
        // return "true" if "p1" is ordered
        // before "p2", for example:
        return p1.height < p2.height;
    }
};

int main()
{
    priority_queue<Person, vector<Person>, CompareHeight> Q;

    // When we use priority_queue with  structure
    // then we need this kind of syntax where
    // CompareHeight is the functor or comparison function
    float arr[ROW][COL] = { { 30, 5.5 }, { 25, 5 },
                    { 20, 6 }, { 33, 6.1 }, { 23, 5.6 } };

    for (int i = 0; i < ROW; ++ i) {

        Q.push(Person(arr[i][0], arr[i][1]));

        // insert an object in priority_queue by using
        // the Person structure constructor
    }

    while (!Q.empty()) {
        Person p = Q.top();
        Q.pop();
        cout << p.age << " " << p.height << "\n";
    }
    return 0;
}
```

**输出:**

```cpp
33 6.1
20 6
23 5.6
30 5.5
25 5
```

下面给出了使用类实现优先级队列

## C++

```cpp
// program in c++ to use priority_queue with class
#include <iostream>
#include <queue>
using namespace std;

#define ROW 5
#define COL 2

class Person {

public:
    int age;

    float height;

    // this is used to initialize the variables of the class
    Person(int age, float height)
        : age(age), height(height)
    {
    }
};

// we are doing operator overloading through this
bool operator<(const Person& p1, const Person& p2)
{

    // this will return true when second person
    // has greater height. Suppose we have p1.height=5
    // and p2.height=5.5 then the object which
    // have max height will be at the top(or
    // max priority)
    return p1.height < p2.height;
}

int main()
{

    priority_queue<Person> Q;

    float arr[ROW][COL] = { { 30, 5.5 }, { 25, 5 },
               { 20, 6 }, { 33, 6.1 }, { 23, 5.6 } };

    for (int i = 0; i < ROW; ++ i) {

        Q.push(Person(arr[i][0], arr[i][1]));

        // insert an object in priority_queue by using
        // the Person class constructor
    }

    while (!Q.empty()) {

        Person p = Q.top();

        Q.pop();

        cout << p.age << " " << p.height << "\n";
    }
    return 0;
}
```

**输出:**

```cpp
33 6.1
20 6
23 5.6
30 5.5
25 5
```