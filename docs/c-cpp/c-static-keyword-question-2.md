# C++ |静态关键词|问题 2

> 原文:[https://www.geeksforgeeks.org/c-static-keyword-question-2/](https://www.geeksforgeeks.org/c-static-keyword-question-2/)

```cpp
#include <iostream>
using namespace std;

class Player
{
private:
    int id;
    static int next_id;
public:
    int getID() { return id; }
    Player()  {  id = next_id++ ; }
};
int Player::next_id = 1;

int main()
{
  Player p1;
  Player p2;
  Player p3;
  cout << p1.getID() << " ";
  cout << p2.getID() << " ";
  cout << p3.getID();
  return 0;
}
```

**(A)** 编译器错误
**(B)**1 2 3
**(C)**1 1 1
**(D)**3 3 3
**(E)**0 0

**回答:****(B)**

**解释:**如果一个成员变量声明为静态，则所有对象静态变量有时被称为类变量、类字段或类范围字段，因为它们不属于特定的对象；他们属于这个班。

在上面的代码中，静态变量 next_id 用于为所有对象分配唯一的 id。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)