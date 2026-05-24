# <utility>在 C++ 中</utility>

> 原文:[https://www.geeksforgeeks.org/utility-in-c/](https://www.geeksforgeeks.org/utility-in-c/)

它是一个头文件，包含不相关域中的实用程序。

*   **对**:这些是可以保存两种不同类型值的对象。
*   **泛型关系方法**:用于关系运算符！=，>，=在特定的名称空间下:rel_ops。
*   **泛型交换函数**:这是标准库的组件默认使用的标准定义，适用于所有不提供自身重载的类型:交换。

**功能:**

**1。交换**:交换两个对象的值。

## C++

```cpp
// CPP program to illustrate
// the use of swap function
#include <iostream>    
#include <utility>    
using namespace std;

// Driver Program
int main ()
{

    // a: _ _ _ _ (empty array in beginning)
    int a[4];        

    // Initializing, a: _ _ _ _ & b: 10 20 30 40
    int b[] = {10, 20, 30, 40};

    // After swapping, a: 10 20 30 40 & b: _ _ _ _
    swap(a, b);            

    cout << "a contains:";
    for (int i; i<4;i++)
        cout << a[i]<<endl;

    return 0;
}
```

输出:

```cpp
a contains:10
20
30
40
```

**2。make_pair** :它构建了一个第一个元素设置为 x，第二个元素设置为 y 的对。

## C++

```cpp
// CPP program to illustrate
// the use of make_pair
#include <utility>    
#include <iostream>
using namespace std;

// Driver program
int main ()
{

    // Initializing the pair with int type
    pair <int, int> a;
    pair <int, int> b;

    // Use of the make_pair function
    a = make_pair (10, 20);

    // It's ok to write like this as implicit
    // conversion takes place from pair<double, char>
    b = make_pair (15.5, 'B');

    // Printing the first and second values of the pair
    cout << "a: " << a.first << ", " << a.second << endl;
    cout << "b: " << b.first << ", " << b.second << endl;

    return 0;
}
```

输出:

```cpp
a: 10, 20
b: 15, 66
```

**3。移动**:随着[右移](https://en.wikipedia.org/wiki/Value_(computer_science))移动。move 用于指示对象可能被“移出”，即允许将资源从一个对象(将被移动)转移到另一个对象。

## C++

```cpp
// CPP program to illustrate
// the use of move
#include <utility>    
#include <iostream>    
#include <vector>    
#include <string>    
using namespace std;

// Driver Program
int main ()
{
    string s = "Hello!!";
    string s1 = "I am a geek.";
    vector<string> gfg;

    // It copies 's' in gfg
    gfg.push_back (s);

    // It moves 's1' in the gfg(containing 's')
    gfg.push_back (move(s1));        

    cout << "gfg contains:";
    for (int i=0;i< gfg.size(); i++)
        cout << ' ' << gfg[i];
    cout<<endl;

    return 0;
}
```

输出:

```cpp
gfg contains: Hello!! I am a geek.
```

**4。移动(元素范围)**:将**【第一个，最后一个】**范围内的元素移动到从结果开始的范围内。
此操作后，移动自范围内的元素仍将包含适当类型的有效值，但不一定与移动前的值相同。

## C++

```cpp
// CPP program to
// Illustrate the use of vector
// move range of elements
#include <iostream>

// for move (ranges)
#include <algorithm>

// for move (objects)
#include <utility>    
#include <vector>    
#include <string>
using namespace std;

// Driver program
int main ()
{
    vector<string> string1 = {"Hello!", "I", "am", "a", "geek"};
    vector<string> string2 (5);

    // moving ranges:
    cout << "Moving ranges...\n";

    // use of move i.e.it moves from first to last element in
    // string 1 to the string2 from it's(string 2) starting
    move ( string1.begin(), string1.begin()+5, string2.begin() );

    cout << "string1 contains " << string1.size()
                                << " elements\n";

    cout << "string2 contains " << string2.size()
                        << " elements(after moving):";

    for (int i=0; i<string2.size(); i++)
        cout << string2[i] << " ";
    cout << endl;

    return 0;
}
```

输出:

```cpp
Moving ranges...
string1 contains 5 elements
string2 contains 5 elements(after moving):Hello! I am a geek 
```

**5。move_if_noexcept** :如果它的 move 构造函数没有抛出异常，它会获得对其参数的右值引用，否则会获得对其参数的左值引用。

## C++

```cpp
// CPP program to illustrate
// the use of move_if_noexcept
#include<iostream>
#include<utility>
using namespace std;

struct Bad
{

    Bad() {}

    // may throw
    Bad(Bad&&)
    {
        cout << "Throwing move constructor called"<<endl;
    }

    // may throw as well
    Bad(const Bad&)
    {
        cout << "Throwing copy constructor called"<<endl;
    }
};

struct Good
{
    Good() {}

    // will NOT throw
    Good(Good&&) noexcept
    {
        cout << "Non-throwing move constructor called"<<endl;
    }

    // will NOT throw
    Good(const Good&) noexcept
    {
        cout << "Non-throwing copy constructor called"<<endl;
    }
};

// Driver Program
int main()
{
    Good g;
    Bad b;
    Good g2 = move_if_noexcept(g);
    Bad b2 = move_if_noexcept(b);
}
```

输出:

```cpp
Non-throwing move constructor called
Throwing copy constructor called
```

**6。decval** :返回一个右值引用，不引用任何对象。
如果一个参数的移动构造函数从不抛出，这个函数选择该参数的类型作为右值引用，或者如果该类型是可复制构造的，这个函数选择左值引用。如果两个类型都不是，函数返回一个右值，该值将被选择用于只移动类型(即使它们可能抛出)。
有些操作既可以通过移动来实现，也可以通过复制对象来实现，一般为右值移动，为左值复制:当不再需要对象(如右值)时，移动一般是比复制更有效的操作。

## C++

```cpp
// CPP program to illustrate
// the use of declval
#include <utility>
#include <iostream>
using namespace std;

//class
struct A
{
virtual int value() = 0;
};

// Class with constructor
class B : public A
{
    int val_;
    public:
    B(int i, int j):val_(i*j){}
    int value()
    {
        return val_;

    }
};

// Driver Program
int main()
{
    // int a
    decltype(declval<A>().value()) a;

    // int b
    decltype(declval<B>().value()) b;

    //same as constructor
    a = b = B(100, 20).value();
    cout << a << endl;
    return 0;
}
```

输出:

```cpp
2000
```

本文由 [**香巴拉维·辛格**](https://www.facebook.com/shambhavi.singh.1217) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。