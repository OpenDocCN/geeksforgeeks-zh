# c++ 中的递增(++)和递减(–)运算符重载

> 原文:[https://www . geesforgeks . org/increment-and-减量-operator-overload-in-c/](https://www.geeksforgeeks.org/increment-and-decrement-operator-overloading-in-c/)

[运算符重载](https://www.geeksforgeeks.org/operator-overloading-c/)是[面向对象编程](https://www.geeksforgeeks.org/basic-concepts-of-object-oriented-programming-using-c/)的一个特性，它允许程序员重新定义内置的[运算符](https://www.geeksforgeeks.org/operators-c-c/)来处理[用户定义的数据类型](https://www.geeksforgeeks.org/user-defined-derived-data-types-in-c/)。
**为什么操作员超载？**
假设我们定义了一个 Integer 类来处理整数上的操作。我们可以让函数 add()、减法()、乘法()和除法()来处理各自的运算。但是，为了使代码更直观，增强可读性，最好使用与给定操作(+、-、*、/分别对应的运算符，即我们可以替换以下代码
**示例:**

```cpp
Replace
i5 = divide(add(i1, i2), subtract(i3, i4))

by a simpler code:
i5 = (i1 + i2) / (i3 - i4) 
```

### 过载[增量运算符](https://www.geeksforgeeks.org/pre-increment-and-post-increment-in-c/)

[**前缀(+i)** 和**后缀(i++)**](https://www.geeksforgeeks.org/pre-increment-and-post-increment-in-c/) 的运算符符号相同。因此，我们需要两个不同的函数定义来区分它们。这是通过在后缀版本中传递伪 int 参数来实现的。
下面是演示相同的代码。
**预增量过载**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// prefix increment operator overloading

#include <bits/stdc++.h>
using namespace std;

class Integer {
private:
    int i;

public:
    // Parameterised constructor
    Integer(int i = 0)
    {
        this->i = i;
    }

    // Overloading the prefix operator
    Integer operator++()
    {
        Integer temp;
        temp.i = ++ i;
        return temp;
    }

    // Function to display the value of i
    void display()
    {
        cout << "i = " << i << endl;
    }
};

// Driver function
int main()
{
    Integer i1(3);

    cout << "Before increment: ";
    i1.display();

    // Using the pre-increment operator
    Integer i2 = ++ i1;

    cout << "After pre increment: ";
    i2.display();
}
```

**Output:** 

```cpp
Before increment: i = 3
After pre increment: i = 4
```

**增量后过载**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// postfix increment operator overloading

#include <bits/stdc++.h>
using namespace std;

class Integer {
private:
    int i;

public:
    // Parameterised constructor
    Integer(int i = 0)
    {
        this->i = i;
    }

    // Overloading the postfix operator
    Integer operator++(int)
    {
        Integer temp;
        temp.i = i++ ;
        return temp;
    }

    // Function to display the value of i
    void display()
    {
        cout << "i = " << i << endl;
    }
};

// Driver function
int main()
{
    Integer i1(3);

    cout << "Before increment: ";
    i1.display();

    // Using the post-increment operator
    Integer i2 = i1++ ;

    cout << "After post increment: ";
    i2.display();
}
```

**Output:** 

```cpp
Before increment: i = 3
After post increment: i = 3
```

### 使[递减运算符](https://www.geeksforgeeks.org/pre-increment-and-post-increment-in-c/)过载

同样我们也可以如下重载减量操作符
**预减量重载**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// prefix decrement operator overloading

#include <bits/stdc++.h>
using namespace std;

class Integer {
private:
    int i;

public:
    // Parameterised constructor
    Integer(int i = 0)
    {
        this->i = i;
    }

    // Overloading the prefix operator
    Integer operator--()
    {
        Integer temp;
        temp.i = --i;
        return temp;
    }

    // Function to display the value of i
    void display()
    {
        cout << "i = " << i << endl;
    }
};

// Driver function
int main()
{
    Integer i1(3);

    cout << "Before decrement: ";
    i1.display();

    // Using the pre-decrement operator
    Integer i2 = --i1;

    cout << "After pre decrement: ";
    i2.display();
}
```

**Output:** 

```cpp
Before decrement: i = 3
After pre decrement: i = 2
```

**减量后过载**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// postfix decrement operator overloading

#include <bits/stdc++.h>
using namespace std;

class Integer {
private:
    int i;

public:
    // Parameterised constructor
    Integer(int i = 0)
    {
        this->i = i;
    }

    // Overloading the postfix operator
    Integer operator--(int)
    {
        Integer temp;
        temp.i = i--;
        return temp;
    }

    // Function to display the value of i
    void display()
    {
        cout << "i = " << i << endl;
    }
};

// Driver function
int main()
{
    Integer i1(3);

    cout << "Before decrement: ";
    i1.display();

    // Using the post-decrement operator
    Integer i2 = i1--;

    cout << "After post decrement: ";
    i2.display();
}
```

**Output:** 

```cpp
Before decrement: i = 3
After post decrement: i = 3
```