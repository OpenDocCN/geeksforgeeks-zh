# 在 C++ 中重新解释 _ cast | Type Casting 运算符

> 原文:[https://www . geesforgeks . org/re interpret _ cast-in-c-type-casting-operators/](https://www.geeksforgeeks.org/reinterpret_cast-in-c-type-casting-operators/)

**重新解释 _cast** 是 C++ 中使用的一种类型的铸造运算符。

*   它用于将某种数据类型的指针转换为另一种数据类型的指针，即使转换前后的数据类型不同。
*   它不检查指针类型和指针指向的数据是否相同。

**语法:**

```cpp
data_type *var_name = 
       reinterpret_cast <data_type *>(pointer_variable);
```

**返回类型**

*   它没有任何返回类型。它只是转换指针类型。

**参数**

*   它只需要一个参数，即源指针变量(上例中的 p)。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of
// reinterpret_cast
#include <iostream>
using namespace std;

int main()
{
    int* p = new int(65);
    char* ch = reinterpret_cast<char*>(p);
    cout << *p << endl;
    cout << *ch << endl;
    cout << p << endl;
    cout << ch << endl;
    return 0;
}
```

**Output:** 

```cpp
65
A
0x1609c20
A
```

**使用重新解释 _cast 的目的**

1.  reinterpret_cast 是一种非常特殊且危险的铸造操作符类型。建议使用适当的数据类型，即(指针数据类型应与原始数据类型相同)。
2.  它可以将任何指针类型转换为任何其他数据类型。
3.  当我们想处理比特时，就使用它。
4.  如果我们使用这种类型的铸件，那么它就变成了一种非便携式产品。所以，建议不要使用这个概念，除非需要。
5.  它仅用于将任何指针类型转换为其原始类型。
6.  布尔值将被转换为整数值，即 0 表示假，1 表示真。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate using structure
#include <bits/stdc++.h>
using namespace std;

// creating structure mystruct
struct mystruct {
    int x;
    int y;
    char c;
    bool b;
};

int main()
{
    mystruct s;

    // Assigning values
    s.x = 5;
    s.y = 10;
    s.c = 'a';
    s.b = true;

    // data type must be same during casting
    // as that of original

    // converting the pointer of 's' to,
    // pointer of int type in 'p'.
    int* p = reinterpret_cast<int*>(&s);

    cout << sizeof(s) << endl;

    // printing the value currently pointed by *p
    cout << *p << endl;

    // incrementing the pointer by 1
    p++ ;

    // printing the next integer value
    cout << *p << endl;

    p++ ;

    // we are casting back char * pointed
    // by p using char *ch.
    char* ch = reinterpret_cast<char*>(p);

    // printing the character value
    // pointed by (*ch)
    cout << *ch << endl;

    ch++ ;

    /* since, (*ch) now points to boolean value,
    so it is required to access the value using
    same type conversion.so, we have used
    data type of *n to be bool. */

    bool* n = reinterpret_cast<bool*>(ch);
    cout << *n << endl;

    // we can also use this line of code to
    // print the value pointed by (*ch).
    cout << *(reinterpret_cast<bool*>(ch));

    return 0;
}
```

**Output:** 

```cpp
12
5
10
a
1
1
```

**节目 2**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate the pointer reinterpret
#include <iostream>
using namespace std;

class A {
public:
    void fun_a()
    {
        cout << " In class A\n";
    }
};

class B {
public:
    void fun_b()
    {
        cout << " In class B\n";
    }
};

int main()
{
    // creating object of class B
    B* x = new B();

    // converting the pointer to object
    // referenced of class B to class A
    A* new_a = reinterpret_cast<A*>(x);

    // accessing the function of class A
    new_a->fun_a();
    return 0;
}
```

**Output:** 

```cpp
In class A
```

**相关链接:**
[https://www . geeksforgeeks . org/casting-operators-in-c-set-1-const _ cast/](https://www.geeksforgeeks.org/casting-operators-in-c-set-1-const_cast/)
[https://stackoverflow . com/questions/573294/何时使用-重新解释-cast " rel = " noopener " target = " _ blank](https://stackoverflow.com/questions/573294/when-to-use-reinterpret-cast)
[http://forums.codeguru.com/showthread.php?482227-re interpret _ cast-lt-gt-以及可以使用的位置](http://forums.codeguru.com/showthread.php?482227-reinterpret_cast-lt-gt-and-where-can-it-be-used)
[https://www . IBM . com/support/knowledge center/en/SSLTBW _ 2 . 3 . 0/com . IBM . zos . v2r 3 . cbclx 01/keyword _ re interpret _ cast . htm](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.3.0/com.ibm.zos.v2r3.cbclx01/keyword_reinterpret_cast.htm)
[https://stackeoverflow . com/questions/573294/when-to](https://stackoverflow.com/questions/573294/when-to-use-reinterpret-cast)