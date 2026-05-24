# c++ 中的模板和静态变量

> 原文:[https://www . geesforgeks . org/templates-and-static-variables-in-c/](https://www.geeksforgeeks.org/templates-and-static-variables-in-c/)

**函数模板和静态变量:**
函数模板的每个实例化都有自己的局部静态变量副本。例如，在下面的程序中有两个实例:*虚空乐趣(int )* 和*虚空乐趣(double )* 。所以静态变量 *i* 存在两个副本。

```cpp
#include <iostream>

using namespace std;

template <typename T>
void fun(const T& x)
{
  static int i = 10;
  cout << ++ i;
  return;
}

int main()
{    
  fun<int>(1);  // prints 11
  cout << endl;
  fun<int>(2);  // prints 12
  cout << endl;
  fun<double>(1.1); // prints 11
  cout << endl;
  getchar();
  return 0;
}
```

上述程序的输出是:

```cpp
  11
  12
  11

```

**类模板和静态变量:**
类模板的规则与函数模板相同
类模板的每个实例化都有自己的成员静态变量副本。例如，在下面的程序中有两个实例*测试*和*测试*。所以静态变量*计数*存在两个副本。

```cpp
#include <iostream>

using namespace std;

template <class T> class Test
{  
private:
  T val; 
public:
  static int count;
  Test()
  {
    count++ ;
  }
  // some other stuff in class
};

template<class T>
int Test<T>::count = 0;

int main()
{
  Test<int> a;  // value of count for Test<int> is 1 now
  Test<int> b;  // value of count for Test<int> is 2 now
  Test<double> c;  // value of count for Test<double> is 1 now
  cout << Test<int>::count   << endl;  // prints 2  
  cout << Test<double>::count << endl; //prints 1

  getchar();
  return 0;
}
```

上述程序的输出是:

```cpp
  2
  1

```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。