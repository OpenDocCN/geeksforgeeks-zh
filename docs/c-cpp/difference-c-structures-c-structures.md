# C 结构和 C++ 结构的区别

> 原文:[https://www . geesforgeks . org/difference-c-structures-c-structures/](https://www.geeksforgeeks.org/difference-c-structures-c-structures/)

虽然 C++ 是 C 的子集，但是，C 中的结构和 C++ 中的结构有什么区别呢？在 C++ 中，结构类似于类。一个主要的区别是，在 C 中，结构的成员默认为公共可见性，但是在 C++ 中，结构的成员默认为私有可见性。

## **C 和 C++ 结构之间的差异**

<figure class="table">

| 

结构

 | 

C++ 结构

 |
| --- | --- |
| 只允许数据成员，它不能有成员函数。 | 可以同时持有:成员函数和数据成员。 |
| 不能有静态成员。 | 可以有静态成员。 |
| 结构中不能有构造函数。 | 允许创建构造函数。 |
| 数据成员的直接初始化是不可能的。 | 数据成员的直接初始化是可能的。 |
| 要声明结构类型变量，必须编写“struct”关键字。 | 声明结构类型变量时，不必写入“struct”关键字。 |
| 没有访问修饰符。 | 支持访问修饰符。 |
| 只允许指向结构的指针。 | 可以有指向结构的指针和引用。 |
| Sizeof 运算符将为空结构生成 0。 | Sizeof 运算符将为空结构生成 1。 |
| 数据隐藏是不可能的。 | 数据隐藏是可能的。 |

</figure>

**1。** **结构内的成员函数**:C 中的结构不能在结构内有成员函数，但是 C++ 中的结构可以有成员函数和数据成员。

## C

```cpp
// C Program to Implement Member
// functions inside structure

#include <stdio.h>

struct marks {
    int num;

    // Member function inside Structure to
    // take input and store it in "num"
    void Set(int temp) { num = temp; }

    // function used to display the values
    void display() { printf("%d", num); }
};

// Driver Program
int main()
{
    struct marks m1;
    // calling function inside Struct to
    // initialize value to num
    m1.Set(9);

    // calling function inside struct to
    // display value of Num
    m1.display();
}
```

**输出**

```cpp
This will generate an error in C but no error in C++. 
```

## C++

```cpp
// C++ Program to Implement Member functions inside
// structure

#include <iostream>
using namespace std;

struct marks {
    int num;

    // Member function inside Structure to
    // take input and store it in "num"
    void Set(int temp) { num = temp; }

    // function used to display the values
    void display() { cout << "num=" << num; }
};

// Driver Program
int main()
{
    marks m1;

    // calling function inside Struct to
    // initialize value to num
    m1.Set(9);

    // calling function inside struct to
    // display value of Num
    m1.display();
}
```

**Output**

```cpp
num=9
```

**2。静态成员:** C 结构不能有静态成员，但在 C++ 中是允许的。

## C

```cpp
// C program with structure static member

struct Record {
    static int x;
};

// Driver program
int main() { return 0; }
```

## C++

```cpp
// C++ program with structure static member

struct Record {
    static int x;
};

// Driver program
int main() { return 0; }
```

*这将在 C 中产生一个错误，但在 C++ 中不会。*

**3。结构中的构造函数创建:**C 中的结构不能在结构中有构造函数，但是 C++ 中的结构可以有构造函数创建。

## C

```cpp
// C program to demonstrate that
// Constructor is not allowed

#include <stdio.h>

struct Student {
    int roll;
    Student(int x) { roll = x; }
};

// Driver Program
int main()
{
    struct Student s(2);
    printf("%d", s.x);
    return 0;
}
```

## C++

```cpp
// CPP program to initialize data member in c++
#include <iostream>
using namespace std;

struct Student {
    int roll;
    Student(int x) { roll = x; }
};

// Driver Program
int main()
{
    struct Student s(2);
    cout << s.roll;
    return 0;
}
```

*这将在 C.* 中产生一个错误

**c++ 输出:**

```cpp
2
```

**4。直接初始化:**我们不能用 C 直接初始化结构数据成员，但是可以用 C++ 来实现。

## C

```cpp
// C program to demonstrate that direct
// member initialization is not possible in C

#include <stdio.h>

struct Record {
    int x = 7;
};

// Driver Program
int main()
{
    struct Record s;
    printf("%d", s.x);
    return 0;
}
```

## C++

```cpp
// CPP program to initialize data member in c++
#include <iostream>
using namespace std;

struct Record {
    int x = 7;
};

// Driver Program
int main()
{
    Record s;
    cout << s.x << endl;
    return 0;
}
```

*这将在 C.* 中产生一个错误

**c++ 输出:**

```cpp
7
```

**5。使用 struct 关键字:**在 C 语言中，我们需要使用一个 struct 来声明一个 struct 变量。在 C++ 中，结构不是必需的。例如，让记录有一个结构。在 C 语言中，我们必须对记录变量使用“结构记录”。在 C++ 中，我们不需要使用结构，只使用“记录”就可以了。

**6。访问修饰符:** C 结构没有访问修饰符，因为语言不支持这些修饰符。C++ 结构可以有这个概念，因为它内置在语言中。

**7。指针和引用:**在 C++ 中，可以有指向 C++ 中一个结构的指针和引用，但在 C 中只允许指向结构的指针。

**8。sizeof 运算符:**该运算符将为 C++ 中的空结构生成 **0** ，而为 c++ 中的空结构生成 **1** 。

## C

```cpp
// C program to illustrate empty structure

#include <stdio.h>

// empty structure
struct Record {
};

// Driver Code
int main()
{
    struct Record s;
    printf("%lu\n", sizeof(s));
    return 0;
}
```

## C++

```cpp
// C++ program to illustrate empty structure
#include <iostream>
using namespace std;

// empty structure
struct Record {
};

// Driver program
int main()
{
    struct Record s;
    cout << sizeof(s);
    return 0;
}

// This code is contributed by Shubham Sharma
```

**C 中的输出:**

```cpp
0
```

**c++ 输出:**

```cpp
1
```

> **注意:**sizeof 的默认类型是长无符号 int，这就是 printf 函数中使用“%lu”而不是“%d”的原因。

**9。数据隐藏:** C 结构不允许数据隐藏的概念，但在 C++ 中是允许的，因为它是一种面向对象的语言，而 C 则不是。

**相关文章:**[c++ 中结构 vs 类](https://www.geeksforgeeks.org/g-fact-76/)

本文由 **Shubham Chaudhary** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。