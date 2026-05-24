# C++ |运算符重载|问题 10

> 原文:[https://www . geesforgeks . org/c-operator-overload-question-10/](https://www.geeksforgeeks.org/c-operator-overloading-question-10/)

以下哪个运算符函数不能是全局的，即必须是成员函数。
**(A)** 新增
**(B)** 删除
**(C)** 转换运算符
**(D)** 以上所有的

**回答:****(C)**

T21】说明:新增和删除都可以是全局的，请看下面的例子。

```cpp

#include
#include
#include

using namespace std;

class Myclass {
    int x;
public:
    friend void* operator new(size_t size);
    friend void operator delete(void*);
    Myclass(int i) {
        x = i;
        cout << "Constructor called \n";
    }
    ~Myclass() { cout << "Destructor called \n"; }
};

void* operator new(size_t size)
{
    void *storage = malloc(size);
    cout << "new called \n";
    return storage;
}

void operator delete(void *p )
{
    cout<<"delete called \n";
    free(p);
}

int main()
{
    Myclass *m = new Myclass(5);
    delete m;
    return 0;
}

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)