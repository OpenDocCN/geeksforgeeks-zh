# c++ 中 main()可以重载吗？

> 原文:[https://www.geeksforgeeks.org/can-main-overloaded-c/](https://www.geeksforgeeks.org/can-main-overloaded-c/)

预测后续 C++ 程序的输出。

```cpp
#include <iostream>
using namespace std;
int main(int a)
{
    cout << a << "\n";
    return 0;
}
int main(char *a)
{
    cout << a << endl;
    return 0;
}
int main(int a, int b)
{
    cout << a << " " << b;
    return 0;
}
int main()
{
    main(3);
    main("C++");
    main(9, 6);
    return 0;
}
```

上述程序编译失败，产生警告和错误(产生的警告和错误见[本](http://ideone.com/SFhsE7))。你可能会在不同的编译器上得到不同的错误。

要在 C++ 中重载 main()函数，需要使用类并将 main 声明为成员函数。请注意，在 C、C++、Java 和 C#等编程语言中，main 不是保留字。例如，我们可以声明一个名为 main 的变量，试试下面的例子:

```cpp
#include <iostream>
int main()
{
    int main = 10;
    std::cout << main;
    return 0;
}
```

输出:

```cpp
10
```

下面的程序展示了一个类中 main()函数的重载。

```cpp
#include <iostream>
using namespace std;
class Test
{
public:
    int main(int s)
    {
        cout << s << "\n";
        return 0;
    }
    int main(char *s)
    {
        cout << s << endl;
        return 0;
    }
    int main(int s ,int m)
    {
        cout << s << " " << m;
        return 0;
    }
};
int main()
{
    Test obj;
    obj.main(3);
    obj.main("I love C++");
    obj.main(9, 6);
    return 0;
}
```

节目的结果是:

```cpp
3
I love C++
9 6
```

本文由 **Pravasi Meet** 供稿。如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论