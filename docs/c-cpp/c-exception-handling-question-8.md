# C++ |异常处理|问题 8

> 原文:[https://www . geesforgeks . org/c-异常处理-问题-8/](https://www.geeksforgeeks.org/c-exception-handling-question-8/)

```cpp
#include <iostream>
using namespace std;

class Test {
public:
   Test() { cout << "Constructing an object of Test " << endl; }
  ~Test() { cout << "Destructing an object of Test "  << endl; }
};

int main() {
  try {
    Test t1;
    throw 10;
  } catch(int i) {
    cout << "Caught " << i << endl;
  }
}
```

**(甲)**

```cpp
Caught 10
```

**(B)**

```cpp
Constructing an object of Test 
Caught 10
```

**(C)**

```cpp
Constructing an object of Test 
Destructing an object of Test 
Caught 10
```

**(D)** 编译器错误

**回答:** **(C)**

**解释:**当在 try 块内部创建对象时，在将控制权转移到 catch 块之前会调用该对象的析构函数。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)