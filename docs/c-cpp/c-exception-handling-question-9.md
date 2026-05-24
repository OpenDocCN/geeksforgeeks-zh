# C++ |异常处理|问题 9

> 原文:[https://www . geesforgeks . org/c-异常处理-问题-9/](https://www.geeksforgeeks.org/c-exception-handling-question-9/)

```cpp
#include <iostream>
using namespace std;

class Test {
  static int count;
  int id;
public:
  Test() {
    count++ ;
    id = count;
    cout << "Constructing object number " << id << endl;
    if(id == 4)
       throw 4;
  }
  ~Test() { cout << "Destructing object number " << id << endl; }
};

int Test::count = 0;

int main() {
  try {
    Test array[5];
  } catch(int i) {
    cout << "Caught " << i << endl;
  }
}
```

**(甲)**

```cpp
Constructing object number 1
Constructing object number 2
Constructing object number 3
Constructing object number 4
Destructing object number 1
Destructing object number 2
Destructing object number 3
Destructing object number 4
Caught 4
```

**(B)**

```cpp
Constructing object number 1
Constructing object number 2
Constructing object number 3
Constructing object number 4
Destructing object number 3
Destructing object number 2
Destructing object number 1
Caught 4
```

**(C)**

```cpp
Constructing object number 1
Constructing object number 2
Constructing object number 3
Constructing object number 4
Destructing object number 4
Destructing object number 3
Destructing object number 2
Destructing object number 1
Caught 4
```

**(D)**

```cpp
Constructing object number 1
Constructing object number 2
Constructing object number 3
Constructing object number 4
Destructing object number 1
Destructing object number 2
Destructing object number 3
Caught 4
```

**回答:** **(B)**

**说明:**析构函数的调用顺序与构造函数相反。此外，在 try 块之后，析构函数只对完全构造的对象调用。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)