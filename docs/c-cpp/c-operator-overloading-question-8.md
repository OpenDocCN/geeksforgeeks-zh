# C++ |运算符重载|问题 10

> 原文:[https://www . geesforgeks . org/c-operator-overload-question-8/](https://www.geeksforgeeks.org/c-operator-overloading-question-8/)

预测产量？

```cpp
#include<stdlib.h>
#include<stdio.h>
#include<iostream>

using namespace std;

class Test {
    int x;
public:
    void* operator new(size_t size);
    void operator delete(void*);
    Test(int i) {
        x = i;
        cout << "Constructor called \n";
    }
    ~Test() { cout << "Destructor called \n"; }
};

void* Test::operator new(size_t size)
{
    void *storage = malloc(size);
    cout << "new called \n";
    return storage;
}

void Test::operator delete(void *p )
{
    cout<<"delete called \n";
    free(p);
}

int main()
{
    Test *m = new Test(5);
    delete m;
    return 0;
}
```

**(甲)**

```cpp
new called
Constructor called
delete called
Destructor called
```

**(B)**

```cpp
new called
Constructor called
Destructor called
delete called
```

**(C)**

```cpp
Constructor called
new called
Destructor called
delete called
```

**(D)**

```cpp
Constructor called
new called
delete called
Destructor called
```

**回答:** **(B)**

**解释:**考虑以下说法

```cpp
    Test *ptr = new Test;  
```

上面的语句实际上发生了两件事——内存分配和对象构造；**新关键字**负责这两者。过程中的一步是调用**算子新建**以分配内存；另一步是实际调用构造函数。**操作符新增**只允许我们更改内存分配方法，对构造函数调用方法没有任何作用。**关键字新增**负责调用构造函数，而不是**操作符新增**。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)