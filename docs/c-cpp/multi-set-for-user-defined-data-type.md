# 多套自定义数据类型

> 原文:[https://www . geesforgeks . org/用户定义数据类型多集/](https://www.geeksforgeeks.org/multi-set-for-user-defined-data-type/)

给你问问题。每个查询包含一个整数 k 和一个人的信息，即名字、姓氏、年龄。对于每个查询，如果所有的人员信息都按升序排列，我们需要输出其中的第 Kt 个人。
注:如果 **A** 的**名**比 **B** 的名在词典上小，则人 **A** 排在人 **B** 之前。但是如果名字相同，那么我们比较**姓**，如果姓也相同，那么我们必须比较他们的**年龄**。

给定:K 将始终小于或等于出席人数。
示例:

```cpp
Input : Q = 2
        1
        aa bb 10
        2 
        bb cc 10
Output :
First name:aa
Last name:bb
Age: 10

First name:bb
Last name:cc
Age: 10

```

**方法:**按照下面的算法解决上述问题。

*   基本上，每个查询都会给我们一个人的详细信息，我们必须告诉 Kth 这个人它们是否是按升序排列的。
*   **基本做法:**每次查询后，我们对列表进行排序，只打印第 k 个人的详细信息。但是如果我们使用排序来解决上述问题，那么时间复杂度将是 O(q*q*log(q))。即 O(qlog(q))用于每次排序和 q 查询。
*   **优化:**我们可以提高上述问题的时间复杂度。正如我们所知，在[中插入多集](https://www.geeksforgeeks.org/multiset-in-cpp-stl/)可以在 log(n)中完成。
*   因此，只需创建一个可用于存储结构的多集，然后在每次查询后，只需在我们的多集中插入该人的详细信息。
*   所以，这似乎是更好的方法。我们的整体复杂度将是 O(q*log(q))。

```cpp
// CPP program for queries to find k-th person where
// people are considered in lexicographic order of
// first name, then last name, then age
#include <bits/stdc++.h>
using namespace std;

struct person {
    string firstName, lastName;
    int age;
};

// operator overloading to use multiset for user 
// define data type.
bool operator<(person a, person b)
{
    if (a.firstName < b.firstName)
        return true;
    else if (a.firstName == b.firstName) {
        if (a.lastName < b.lastName)
            return true;
        else if (a.lastName == b.lastName) {
            if (a.age < b.age)
                return true;
            else
                return false;
        }
        else
            return false;
    }
    else
        return false;
}

// define function for printing our output
void print(multiset<person>::iterator it)
{
    cout << "First name:" << it->firstName << endl;
    cout << "Last name:" << it->lastName << endl;
    cout << "Age: " << it->age << endl;
}

int main()
{
    int q = 2;

    // define set for structure
    multiset<person> s;

    // declaration of person structure
    person p;

    // 1st Query k=1, first-name=aa, last-name=bb, age=10;
    int k = 1;
    p.firstName = "aa";
    p.lastName = "bb";
    p.age = 10;

    // now insert this structure in our set.
    s.insert(p);

    // now find Kth smallest element in set.
    multiset<person>::iterator it;
    it = s.begin();

    // find kth element by increment iterator by k
    std::advance(it, k - 1);
    print(it);

    // 2nd Query k=2, first-name=bb, last-name=cc, age=10;
    k = 2;
    p.firstName = "bb";
    p.lastName = "cc";
    p.age = 10;

    // now insert this structure in our set.
    s.insert(p);

    // now find Kth smallest element in set.
    it = s.begin();

    // find kth element by increment iterator by k
    std::advance(it, k - 1);
    print(it);
    return 0;
}
```

**Output:**

```cpp
First name:aa
Last name:bb
Age: 10
First name:bb
Last name:cc
Age: 10

```