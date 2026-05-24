# c++ 程序输出|第 36 集

> 原文:[https://www.geeksforgeeks.org/output-c-programs-set-36/](https://www.geeksforgeeks.org/output-c-programs-set-36/)

**问题 1** 。假设 int 的大小是 4 字节，下面的输出是什么？

```cpp
#include <iostream>
using namespace std;

class abc {
    void f();
    void g();
    int x;
};

main()
{
    cout << sizeof(abc) << endl;
}
```

**选项:**
A) 12
B) 4
C) 8
D)编译错误

```cpp
Answer : B
```

**解释:**
只有类成员变量构成为类或其对象的大小。所以在这种情况下，我们必须有一个 int 值，这样类的总大小将是 0 + 0 + 4。(考虑 int 为 4 字节)。

**问题 2** 。下面的输出是什么

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a[] = { 1, 2 }, *p = a;
    cout << p[1];
}
```

**选项:**
A) 1
B) 2
C)编译错误
D)运行时错误

```cpp
Answer : B
```

**说明:**
当我们把数组‘a’赋给指针‘p’时，它会保存数组的基址。我们可以像使用“a”一样使用“p”来访问数组

 **问题 3** 。下面的输出是什么

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a[] = { 10, 20, 30 };
    cout << *a + 1;
}
```

**选项:**T2 A)10
B)20
C)11
D)21

```cpp
Answer : C
```

**解释:**
*a 指 10，加 1 等于 11。

 **Ques 4** 。下面的输出是什么

```cpp
#include <iostream>
using namespace std;

class Box {
    double width;

public:
    friend void printWidth(Box box);
    void setWidth(double wid);
};
void Box::setWidth(double wid)
{
    width = wid;
}
void printWidth(Box box)
{
    box.width = box.width * 2;
    cout << "Width of box : " << box.width << endl;
}
int main()
{
    Box box;
    box.setWidth(10.0);
    printWidth(box);
    return 0;
}
```

**选项:**T2 A)40
B)5
C)10
D)20

```cpp
Answer : D
```

**说明:**
我们之所以使用 friend 函数，是因为要打印框宽的值。这是一个类的私有成员函数，我们不能访问类外的私有成员。
设置宽度(10.0)设置宽度为 10，打印宽度(方框)打印(宽度* 2)即 20。

**问题 5。**以下输出是什么

```cpp
#include <iostream>
using namespace std;
struct a {
    int count;
};
struct b {
    int* value;
};
struct c : public a, public b {
};
int main()
{
    c* p = new c;
    p->value = 0;
    cout << "Inherited";
    return 0;
}
```

**选项:**
A)继承
B)错误
C)运行时错误
D)上述都没有

```cpp
Answer : A
```

**说明:**类或结构‘c’继承类‘a’的同时也继承类‘b’。当我们创建 c 类的对象 p 时，a 和 b 都是自动继承的，这意味着我们可以访问 a 和 b 类的属性。
因此，p- >值将被设置为 0，如问题中所给，然后打印继承的并退出代码。

本文由**里沙布·贾恩**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。