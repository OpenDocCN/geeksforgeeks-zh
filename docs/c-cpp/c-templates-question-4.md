# C++ |模板|问题 4

> 原文:[https://www.geeksforgeeks.org/c-templates-question-4/](https://www.geeksforgeeks.org/c-templates-question-4/)

以下程序的输出？

```cpp
#include <iostream>
using namespace std;

template <class T>
class Test
{
private:
    T val;
public:
    static int count;
    Test()  {   count++ ;   }
};

template<class T>
int Test<T>::count = 0;

int main()
{
    Test<int> a;
    Test<int> b;
    Test<double> c;
    cout << Test<int>::count   << endl;
    cout << Test<double>::count << endl;
    return 0;
}
```

**(甲)**

```cpp
0
0
```

**(B)**

```cpp
1
1
```

**(C)**

```cpp
2
1
```

**(D)**

```cpp
1
0
```

**回答:** **(C)**

**说明:**模板创建了两个类:Test 和 Test。

因为 count 是一个静态成员，所以每个类都有自己的副本。此外，计数在构造函数中递增。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)