# 捕捉基类和派生类作为异常

> 原文:[https://www.geeksforgeeks.org/g-fact-60/](https://www.geeksforgeeks.org/g-fact-60/)

**异常处理–将基类和派生类捕获为异常:**
如果基类和派生类都被捕获为异常，那么派生类的 catch 块必须出现在基类之前。
如果我们把基类放在第一位，那么派生类 catch 块将永远不会到达。例如，下面的 C++ 代码打印出*“捕获到基础异常”*

## C

```cpp
#include<iostream>
using namespace std;

class Base {};
class Derived: public Base {};
int main()
{
   Derived d;
   // some other stuff
   try {
       // Some monitored code
       throw d;
   }
   catch(Base b) {
        cout<<"Caught Base Exception";
   }
   catch(Derived d) {  //This catch block is NEVER executed
        cout<<"Caught Derived Exception";
   }
   getchar();
   return 0;
}
```

在上面的 C++ 代码中，如果我们改变 catch 语句的顺序，那么两个 catch 语句都变得可达。以下是修改后的程序，它打印*“捕获的派生异常”*

## C

```cpp
#include<iostream>
using namespace std;

class Base {};
class Derived: public Base {};
int main()
{
   Derived d;
   // some other stuff
   try {
       // Some monitored code
       throw d;
   }
   catch(Derived d) {
        cout<<"Caught Derived Exception";
   }
   catch(Base b) {
        cout<<"Caught Base Exception";
   }
   getchar();
   return 0;
}
```

在 Java 中，编译器本身不允许在派生之前捕获基类异常。在 C++ 中，编译器可能会给出警告，但会编译代码。
例如，以下 Java 代码编译失败，出现错误消息*“异常派生已经被捕获”*

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
//filename Main.java
class Base extends Exception {}
class Derived extends Base  {}
public class Main {
  public static void main(String args[]) {
    try {
       throw new Derived();
    }
    catch(Base b) {}
    catch(Derived d) {}
  }
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。