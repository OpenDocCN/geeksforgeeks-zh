# main()中的 return 语句 vs exit()

> 原文:[https://www . geesforgeks . org/return-statement-vs-exit-in-main/](https://www.geeksforgeeks.org/return-statement-vs-exit-in-main/)

在 C++ 中，*退出(0)* 和*返回 0* 有什么区别？

当 *exit(0)* 用于退出程序时，不调用局部范围的非静态对象的析构函数。但是如果使用返回 0，则调用析构函数。

**程序 1––使用退出(0)退出**

```cpp
#include<iostream>
#include<stdio.h>
#include<stdlib.h>

using namespace std;

class Test {
public:
  Test() {
    printf("Inside Test's Constructor\n");
  }

  ~Test(){
    printf("Inside Test's Destructor");
    getchar();
  }
};

int main() {
  Test t1;

  // using exit(0) to exit from main
  exit(0);
}
```

输出:
*内部测试的构造器*

**程序 2–使用返回 0 退出**

```cpp
#include<iostream>
#include<stdio.h>
#include<stdlib.h>

using namespace std;

class Test {
public:
  Test() {
    printf("Inside Test's Constructor\n");
  }

  ~Test(){
    printf("Inside Test's Destructor");
  }
};

int main() {
  Test t1;

   // using return 0 to exit from main
  return 0;
}
```

输出:
*内部测试的构造函数
内部测试的析构函数
T4*

调用析构函数有时很重要，例如，如果析构函数有释放资源的代码，比如关闭文件。

请注意，即使我们调用 exit()，静态对象也会被清除。例如，参见以下程序。

```cpp
#include<iostream>
#include<stdio.h>
#include<stdlib.h>

using namespace std;

class Test {
public:
  Test() {
    printf("Inside Test's Constructor\n");
  }

  ~Test(){
    printf("Inside Test's Destructor");
    getchar();
  }
};

int main() {
  static Test t1;  // Note that t1 is static

  exit(0);
}
```

输出:
*内部测试的构造函数
内部测试的析构函数
T4*

由**印度火箭**提供。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。