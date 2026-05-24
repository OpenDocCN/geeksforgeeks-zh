# 使用静态成员函数

统计对象数量

> 原文:[https://www . geesforgeks . org/count-number-objects-use-static-member-function/](https://www.geeksforgeeks.org/count-number-objects-using-static-member-function/)

**先决条件:** [静态变量](https://www.geeksforgeeks.org/static-variables-in-c/)、[静态函数](https://www.geeksforgeeks.org/what-are-static-functions-in-c/)
编写一个程序来设计一个具有名为 showcount()的静态成员函数的类，该函数具有显示该类创建的对象数量的属性。
 **解释:**在这个程序中，我们只是简单地解释静态成员函数的方法。我们可以使用 static 关键字将类成员和成员函数定义为静态的。在理解静态成员函数之前，我们必须了解静态成员。当我们将一个类的成员声明为静态时，这意味着无论创建了多少个该类的对象，静态成员**只有一个副本**。

**关于静态的要点:**

*   静态成员由类的所有对象共享，如果不存在其他初始化，则在创建第一个对象时，所有静态数据都初始化为零。
*   静态成员函数只能从类外部访问静态数据成员、其他静态成员函数和任何其他函数。
*   通过将函数成员声明为静态的，我们使它独立于类的任何特定对象。即使不存在该类的对象，并且只使用类名和范围解析运算符访问静态函数，也可以调用静态成员函数。
*   我们不能把它放在类定义中，但是它可以在类外初始化，如下例所示，通过重新声明静态变量，使用作用域解析运算符::来标识它属于哪个类。

示例:

```cpp
Input : Here  we are not asking for input from the user
Output :count:2
count:3
object number :1
object number :2
object number :3

Input :Here we are not asking for input from the user
Output :count:2
count:3
object number :1
object number :2
object number :3

```

```cpp
// C++ program to Count the number of objects
// using the Static member function
#include <iostream>
using namespace std;
class test {
    int objNo;
    static int objCnt;

public:
    test()
    {
    objNo = ++ objCnt;
    }
    ~test()
    {
    --objCnt;
    }
    void printObjNumber(void)
    {
        cout << "object number :" << objNo << "\n";
    }
    static void printObjCount(void)
    {
        cout << "count:" << objCnt<< "\n";
    }
};
int test::objCnt;
int main()
{
    test t1, t2;
    test::printObjCount();

    test t3;
    test::printObjCount();

    t1.printObjNumber(); 
    t2.printObjNumber(); 
    t3.printObjNumber();
    return 0;
}
```

输出:

```cpp
count:2
count:3
object number :1
object number :2
object number :3

```