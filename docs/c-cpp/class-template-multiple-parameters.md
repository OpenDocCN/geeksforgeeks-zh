# 多参数类模板

> 原文:[https://www . geesforgeks . org/class-template-multi-parameters/](https://www.geeksforgeeks.org/class-template-multiple-parameters/)

前提条件:[c++ 中的模板](https://www.geeksforgeeks.org/templates-cpp/)

创建模板时，可以指定多种类型。我们可以在一个类模板中使用多个通用数据类型。它们在模板中声明为逗号分隔列表，如下所示:
**语法:**

```cpp
template<class T1, class T2, ...>
class classname
{
      ...
      ...
};

```

```cpp
// CPP program to illustrate
// Class template with multiple parameters

#include<iostream>
using namespace std;

// Class template with two parameters
template<class T1, class T2>
class Test
{
        T1 a;
        T2 b;
    public:
        Test(T1 x, T2 y)
        {
            a = x;
            b = y;
        }
        void show()
        {
            cout << a << " and " << b << endl;
        }
};

// Main Function
int main()
{
    // instantiation with float and int type
    Test <float, int> test1 (1.23, 123);

    // instantiation with float and char type
    Test <int, char> test2 (100, 'W');   

    test1.show();
    test2.show();

    return 0;
}
```

输出:

```cpp
1.23 and 123
100 and  W

```

**代码说明:**

*   在上面的程序中，测试构造函数有两个泛型类型的参数。
*   创建对象时，在尖括号 **< >** 中提到了参数的类型。
*   当参数不止一个时，它们用逗号隔开。
*   Following statement

    ```cpp
    Test  test1 (1.23, 123);
    ```

    告诉编译器第一个参数的类型是 **float** ，另一个是 **int** 类型。

*   在创建对象的过程中，调用构造函数，模板参数接收值。

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。