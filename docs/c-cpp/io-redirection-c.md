# c++ 中的 I/O 重定向

> 原文:[https://www.geeksforgeeks.org/io-redirection-c/](https://www.geeksforgeeks.org/io-redirection-c/)

在 C 语言中，我们可以使用函数 [freopen()](http://www.cplusplus.com/reference/cstdio/freopen/) 将现有的文件指针重定向到另一个流。freopen()的原型如下所示

```cpp
FILE * freopen ( const char * filename, const char * mode, FILE * stream );
```

例如，要将标准输出重定向为文本文件，我们可以写

```cpp
freopen ("text_file.txt", "w", stdout);
```

虽然 C++ 仍然支持这种方法，但本文讨论了重定向输入/输出流的另一种方法。
C++ 作为一种面向对象的编程语言，让我们不仅能够定义自己的流，还能够重定向标准流。因此，在 C++ 中，流是其行为由类定义的对象。因此，任何行为像流的东西也是流。
**c++ 中的 Streams 对象主要有三种类型:**

*   **istream :** 这种类型的 stream 对象只能执行来自该流的输入操作
*   **ostream :** 这些对象只能用于输出操作。
*   **iostream :** 可用于输入和输出操作

所有这些类以及文件流类都是从类 ios 和 streambuf 派生的。因此，文件流和输入输出流对象的行为类似。
所有流对象也有一个相关的 streambuf 类的数据成员。简单地说，streambuf 对象是流的缓冲区。当我们从流中读取数据时，我们不是直接从源中读取，而是从链接到源的缓冲区中读取。同样，首先对缓冲区执行输出操作，然后在需要时刷新缓冲区(写入物理设备)。
C++ 允许我们为任何流设置流缓冲区。因此，重定向流的任务只是简化为更改与流相关联的流缓冲区。因此，要将流 A 重定向到流 B，我们需要做的是:-

1.  获取 A 的流缓冲区，并将其存储在某个地方
2.  将 A 的流缓存设置为 B 的流缓存
3.  如果需要将 A 的流缓冲区重置为其先前的流缓冲区

我们可以使用函数 [ios::rdbuf()](http://www.cplusplus.com/reference/ios/ios/rdbuf/) 来执行两个操作。

```cpp
1) stream_object.rdbuf(): Returns pointer to the stream buffer of stream_object
2) stream_object.rdbuf(streambuf * p): Sets the stream buffer to the object pointed by p
```

下面是一个示例程序来展示这些步骤

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Cpp program to redirect cout to a file
#include <fstream>
#include <iostream>
#include <string>

using namespace std;

int main()
{
    fstream file;
    file.open("cout.txt", ios::out);
    string line;

    // Backup streambuffers of  cout
    streambuf* stream_buffer_cout = cout.rdbuf();
    streambuf* stream_buffer_cin = cin.rdbuf();

    // Get the streambuffer of the file
    streambuf* stream_buffer_file = file.rdbuf();

    // Redirect cout to file
    cout.rdbuf(stream_buffer_file);

    cout << "This line written to file" << endl;

    // Redirect cout back to screen
    cout.rdbuf(stream_buffer_cout);
    cout << "This line is written to screen" << endl;

    file.close();
    return 0;
}
```

输出:

```cpp
This line is written to screen
Contents of file cout.txt:
This line written to file
```

**注:**
以上步骤可浓缩为一步

```cpp
auto cout_buf = cout.rdbuf(file.rdbuf())

// sets couts streambuffer and returns the old 
streambuffer back to cout_buf
```

参考资料:[【CPP IOs】](http://www.cplusplus.com/reference/ios/)