# C++ |这个指针|问题 2

> 原文:[https://www.geeksforgeeks.org/c-this-pointer-question-2/](https://www.geeksforgeeks.org/c-this-pointer-question-2/)

这个指针有什么用？
**(A)** 当局部变量的名称与成员名称相同时，我们可以使用这个指针访问成员。
**(B)** 返回对调用对象的引用
**(C)** 可用于对象上的链式函数调用
**(D)** 以上所有

**答案:****(D)**

**解释:**第一次使用见以下示例。

```cpp
/* local variable is same as a member's name */
class Test
{
private:
   int x;
public:
   void setX (int x)
   {
       // The 'this' pointer is used to retrieve the object's x
       // hidden by the local variable 'x'
       this->x = x;
   }
   void print() { cout << "x = " << x << endl; }
};
```

下面是第二点和第三点。

```cpp
#include
using namespace std;

class Test
{
private:
  int x;
  int y;
public:
  Test(int x = 0, int y = 0) { this->x = x; this->y = y; }
  Test &setX(int a) { x = a; return *this; }
  Test &setY(int b) { y = b; return *this; }
  void print() { cout << "x = " << x << " y = " << y << endl; }
};

int main()
{
  Test obj1(5, 5);

  // Chained function calls.  All calls modify the same object
  // as the same object is returned by reference
  obj1.setX(10).setY(20);

  obj1.print();
  return 0;
}

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)