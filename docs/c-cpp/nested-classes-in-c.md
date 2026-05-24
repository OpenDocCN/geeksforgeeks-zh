# c++ 中的嵌套类

> 原文:[https://www.geeksforgeeks.org/nested-classes-in-c/](https://www.geeksforgeeks.org/nested-classes-in-c/)

嵌套类是在另一个封闭类中声明的类。嵌套类是成员，因此具有与任何其他成员相同的访问权限。封闭类的成员对嵌套类的成员没有特殊的访问权限；应当遵守通常的访问规则。

例如，程序 1 编译没有任何错误，程序 2 编译失败。

**程序 1**

```cpp
#include<iostream>

using namespace std;

 /* start of Enclosing class declaration */  
class Enclosing {      
   private:   
       int x;

   /* start of Nested class declaration */  
   class Nested {
      int y;   
      void NestedFun(Enclosing *e) {
        cout<<e->x;  // works fine: nested class can access 
                     // private members of Enclosing class
      }       
   }; // declaration Nested class ends here
}; // declaration Enclosing class ends here

int main()
{     

}
```

**节目 2**

```cpp
#include<iostream>

using namespace std;

 /* start of Enclosing class declaration */  
class Enclosing {      

   int x;

   /* start of Nested class declaration */  
   class Nested {
      int y;   
   }; // declaration Nested class ends here

   void EnclosingFun(Nested *n) {
        cout<<n->y;  // Compiler Error: y is private in Nested
   }      
}; // declaration Enclosing class ends here

int main()
{ 

}
```

参考文献:
[http://www . open-STD . org/JTC 1/sc22/wg21/docs/papers/2005/n 1905 . pdf](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1905.pdf)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。