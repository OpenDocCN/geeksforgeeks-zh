# C++ 可变关键字

> 原文:[https://www.geeksforgeeks.org/c-mutable-keyword/](https://www.geeksforgeeks.org/c-mutable-keyword/)

**C++ 中的可变存储类说明符(或者在 C++ 中使用可变关键字)**
auto、register、static 和 extern 是 C 中的存储类说明符，typedef 也被认为是 C 中的存储类说明符，c++ 也支持所有这些存储类说明符。除了这个 C++，还添加了一个重要的存储类说明符，其名称是可变的。

**易变的需求是什么？**
有时需要通过 const 函数修改类/结构的一个或多个数据成员，即使您不想让该函数更新类/结构的其他成员。这个任务可以很容易地通过使用可变关键字来执行。考虑这个例子，其中使用可变可能是有用的。假设你去酒店，你给服务员点了菜，让他带些菜来。点菜后，你突然决定改变食物的顺序。假设酒店提供设施来改变所订购的食物，并在发出第一份订单后 10 分钟内再次接受新食物的订单。10 分钟后订单不能取消，旧订单不能被新订单取代。有关详细信息，请参见以下代码。

## C++

```cpp
#include <bits/stdc++.h>
#include <string.h>
using namespace std;

// Customer Class
class Customer {

    // class Variables
    string name;
    mutable string placedorder;
    int tableno;
    mutable int bill;

    // member methods
public:

    // constructor
    Customer(string s, string m, int a, int p)
    {
        name= s;
        placedorder=m;
        tableno = a;
        bill = p;
    }

    // to change the place holder
    void changePlacedOrder(string p) const
    {
        placedorder=p;
    }

    // change the bill
    void changeBill(int s) const { bill = s; }

    // to display
    void display() const
    {
        cout << "Customer name is: " << name << endl;
        cout << "Food ordered by customer is: "
             << placedorder << endl;
        cout << "table no is: " << tableno << endl;
        cout << "Total payable amount: " << bill << endl;
    }
};

// Driver code
int main()
{
    const Customer c1("Pravasi Meet", "Ice Cream", 3, 100);
    c1.display();
    c1.changePlacedOrder("GulabJammuns");
    c1.changeBill(150);
    c1.display();
    return 0;
}
```

**Output**

```cpp
Customer name is: Pravasi Meet
Food ordered by customer is: Ice Cream
table no is: 3
Total payable amount: 100
Customer name is: Pravasi Meet
Food ordered by customer is: GulabJammuns
table no is: 3
Total payable amount: 150

```

仔细观察上述程序的输出。*放置器*和*票据*数据成员的值从常量函数更改，因为它们被声明为可变的。

关键字 mutable 主要用于允许修改 const 对象的特定数据成员。[当我们将一个函数声明为 const 时，传递给函数的这个指针变成 const](https://www.geeksforgeeks.org/g-fact-77/) 。向变量添加可变变量允许常量指针改变成员。
如果大多数成员应该是常量，但有少数成员需要更新，那么可变尤其有用。声明为可变的数据成员可以被修改，即使它们是声明为常量的对象的一部分。不能将可变说明符与声明为 static、const 或 reference 的名称一起使用。
作为**练习**预测以下两个程序的输出。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// PROGRAM 1
#include <iostream>
using std::cout;

class Test {
public:
  int x;
  mutable int y;
  Test() { x = 4; y = 10; }
};
int main()
{
    const Test t1;
    t1.y = 20;
    cout << t1.y;
    return 0;
}
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// PROGRAM 2
#include <iostream>
using std::cout;

class Test {
public:
  int x;
  mutable int y;
  Test() { x = 4; y = 10; }
};
int main()
{
    const Test t1;
    t1.x = 8;
    cout << t1.x;
    return 0;
}
```

**来源:**
[可变存储类说明符(仅限 c++)](http://www-01.ibm.com/support/knowledgecenter/SSGH3R_8.0.0/com.ibm.xlcpp8a.doc/language/ref/mutable_storage_class_specifier.htm%23mutable_storage_class_specifier?lang=en)
本文投稿**遇见 Pravasi** 。如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息