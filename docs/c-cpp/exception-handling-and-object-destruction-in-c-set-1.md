# 异常处理和对象销毁|设置 1

> 原文:[https://www . geesforgeks . org/异常处理和对象销毁-in-c-set-1/](https://www.geeksforgeeks.org/exception-handling-and-object-destruction-in-c-set-1/)

预测后续 C++ 程序的输出。

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

输出:

```cpp
  Constructing an object of Test
  Destructing an object of Test
  Caught 10

```

当抛出异常时，在 catch 块被执行之前，对象的析构函数(其作用域以 try 块结束)被自动调用。这就是为什么上面的程序在“捕获 10”之前打印“销毁测试对象”。

当构造函数抛出异常时会发生什么？考虑以下程序。

```cpp
#include <iostream>
using namespace std;

class Test1 {
public:
  Test1() { cout << "Constructing an Object of Test1" << endl; }
  ~Test1() { cout << "Destructing an Object of Test1" << endl; }
};

class Test2 {
public:
  // Following constructor throws an integer exception
  Test2() { cout << "Constructing an Object of Test2" << endl; 
            throw 20; }
  ~Test2() { cout << "Destructing an Object of Test2" << endl; }
};

int main() {
  try {
    Test1 t1;  // Constructed and destructed
    Test2 t2;  // Partially constructed
    Test1 t3;  // t3 is not constructed as this statement never gets executed
  } catch(int i) {
    cout << "Caught " << i << endl;
  }
}
```

输出:

```cpp
  Constructing an Object of Test1
  Constructing an Object of Test2
  Destructing an Object of Test1
  Caught 20

```

析构函数只对完全构造的对象调用。当对象的构造函数引发异常时，不会调用该对象的析构函数。

作为练习，预测以下程序的输出。

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

我们将在另一篇文章中讨论这个话题。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。