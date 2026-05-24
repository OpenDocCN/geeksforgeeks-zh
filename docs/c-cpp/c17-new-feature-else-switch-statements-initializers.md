# C++ 17 新特性:If Else 和 Switch 语句带初始值

> 原文:[https://www . geesforgeks . org/c17-new-feature-else-switch-statements-initializer/](https://www.geeksforgeeks.org/c17-new-feature-else-switch-statements-initializers/)

在许多情况下，我们需要检查函数返回的值，并基于该值执行条件操作。所以我们的代码看起来像这样

```cpp
// Some function
return_type foo(params)

// Call function with params and 
// store return in var
auto var = foo(params);

if (var == /* some value */) { 
   //Do Something
} else {
   //Do Something else
}
```

虽然这没什么，但请注意有一些微妙之处

*   该变量泄漏到周围的范围内，这不是有意的，必须小心确保该变量不会与其他变量混淆
*   由于已经定义了这个变量，如果我们要在程序的后面调用另一个函数(比如 bar())，我们需要创建另一个变量来存储 bar()返回的值
*   第三，如果编译器能够明确知道变量将只在一个 if-else 块中使用，那么它可能能够更好地优化代码。

请注意所有条件 if-else 块的一般格式。首先有一个可选的初始语句来设置变量，然后是 if-else 块。所以一般的 if-else 块类似如下

```cpp
init-statement

if (condition) {
    // Do Something
} else {
   // Do Something else 
}

```

在 C++ 17 中，init 语句被称为初始值设定项，我们可以将其直接放入 if-else 块，如下所示

```cpp
if (init-statement; condition) {
    // Do Something
} else {
    // Do Something else
}

```

条件变量的范围被限制在当前 if-else 块中。这也允许我们在另一个条件块中重用相同的命名标识符。

```cpp
if (auto var = foo(); condition) {
    ...
}
else{
    ...
}

// Another if-else block
if (auto var = bar(); condition) {
    ....
}
else {
    ....
}
```

同样，开关盒也已更新。我们现在可以在开关括号内放一个初始表达式。在初始语句之后，我们需要指定使用哪个变量来检查案例

```cpp
switch (initial-statement; variable) {
    ....
    // cases
}

```

**一个完整的程序**

```cpp
// Program to demonstrate init if-else
// feature introduced in C++ 17
#include <iostream>
#include <cstdlib>
using namespace std;

int main() {

  // Set up rand function to be used
  // later in program
  srand(time(NULL));

  // Before C++ 17
  int i = 2;
  if ( i % 2 == 0)
    cout << i << " is even number" << endl;

  // After C++ 17
  // if(init-statement; condition)
  if (int i = 4; i % 2 == 0  )
    cout << i << " is even number" << endl;

  // Switch statement
  // switch(init;variable)
  switch (int i = rand() % 100; i) {
      default: 
         cout << "i = " << i << endl; break;
  }  
}
```

**输出(机器相关)**

```cpp
2 is even number
4 is even number
i = 5

```

**注意:**要编译这些程序，我们需要最新版本的编译器。在撰写本文时，这个特性已经在 clang 5 和 gcc 7 中完全实现了。为了编译程序，我们还需要指定-std=c++ 17 标志

```cpp
g++-7 program_file.cpp -std=c++ 17

or

clang++ program_file.cpp -std=c++ 17

```