# C++ | Misc C++ |问题 5

> 原文:[https://www.geeksforgeeks.org/c-misc-c-question-5/](https://www.geeksforgeeks.org/c-misc-c-question-5/)

我们怎样才能创建一个 C++ 类，使得它的对象只能用新的操作符来创建？

如果用户试图直接创建一个对象，程序会产生编译器错误。
**(A)** 不可能
**(B)** 通过使析构函数私有
**(C)** 通过使构造函数私有
**(D)** 通过使构造函数和析构函数都私有

**答案:****(B)**

**解释:**见下例。

```cpp
// Objects of test can only be created using new
class Test
{
private:
    ~Test() {}
friend void destructTest(Test* );
};

// Only this function can destruct objects of Test
void destructTest(Test* ptr)
{
    delete ptr;
}

int main()
{
    // create an object
    Test *ptr = new Test;

    // destruct the object
    destructTest (ptr);

    return 0;
}

```

详见[https://www.geeksforgeeks.org/private-destructor/](https://www.geeksforgeeks.org/private-destructor/)。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)