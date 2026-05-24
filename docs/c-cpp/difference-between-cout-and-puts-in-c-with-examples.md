# c++ 中 cout 和 put()的区别，示例

> 原文:[https://www . geeksforgeeks . org/cout-and-puts-in-c-with-examples/](https://www.geeksforgeeks.org/difference-between-cout-and-puts-in-c-with-examples/)

**标准输出流(cout):**[c++ ](https://www.geeksforgeeks.org/c-plus-plus/)**cout**语句是 [ostream 类](https://www.geeksforgeeks.org/c-stream-classes-structure/)的实例。它用于在标准输出设备(通常是显示屏)上显示输出。使用插入操作符( **< <** )将需要在屏幕上显示的数据插入标准输出流( **cout** )。更多详情更喜欢[这篇](https://www.geeksforgeeks.org/basic-input-output-c/)文章。

**[puts()](https://www.geeksforgeeks.org/puts-vs-printf-for-printing-a-string/) :** 可用于打印字符串。它一般比较便宜，如果字符串有像 **'%'** 这样的格式化字符，那么 **printf()** 会给出意想不到的结果。如果字符串**字符串**是用户输入字符串，那么使用 **printf()** 可能会导致安全问题。更多详情更喜欢[这篇](https://www.geeksforgeeks.org/puts-vs-printf-for-printing-a-string/)文章。

**区别为:**

| S.NO | 标准输出 | puts() |
| --- | --- | --- |
| one | 它是 ostream 类的预定义对象。 | puts 是一个预定义函数(库函数)。 |
| Two | cout 是一个对象，它使用重载插入(< | puts 是完整的函数，它没有使用重载的概念。 |
| three | cout 可以同时打印数字和字符串。 | puts 只能打印字符串。 |
| four | 要使用 cout，我们需要包含 iostream.h 头文件。 | 要使用 puts，我们需要包含 stdio.h 头文件。 |

**程序 1:**

## C++

```cpp
// C++ program use of puts
#include <iostream>
#include <stdio.h>
using namespace std;

// main code
int main()
{
    puts("Geeksforgeeks");
    fflush(stdout);
    return 0;
}
```

**Output:**

```cpp
Geeksforgeeks

```

**程序 2:** 下面的程序不需要 fflush 来刷新输出缓冲区，因为 cout 内置了它。

## C++

```cpp
// C++ program use of cout
#include <iostream>
using namespace std;

// main code
int main()
{
    cout << "Geeksforgeeks" << endl;

    return 0;
}
```

**Output:**

```cpp
Geeksforgeeks

```