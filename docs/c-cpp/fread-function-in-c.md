# c++ 中的 fread()函数

> 原文:[https://www.geeksforgeeks.org/fread-function-in-c/](https://www.geeksforgeeks.org/fread-function-in-c/)

C++ 中的 **fread()** 函数从流中读取数据块。这个函数首先从给定的输入流中读取对象的计数，每个对象的大小为大小字节。
成功读取的字节总数为(大小*计数)。根据读取的字符数，指示器文件位置递增。如果读取的对象不是可复制的，那么行为是未定义的，如果大小或计数的值等于零，那么这个程序将简单地返回 0。
**语法:**

```cpp
size_t fread(void * buffer, size_t size, size_t count, FILE * stream)
```

**参数:**该功能接受四个强制参数，描述如下:

*   **缓冲区:**它指定指向大小至少为(size*count)字节的内存块的指针，以存储对象。
*   **大小:**它以字节为单位指定每个对象的大小。 **size_t 是无符号整型。**
*   **计数:**它指定元素的数量，每个元素的大小为大小字节。
*   **流:**指定读取数据的文件流。

**返回值:**函数返回成功读取的对象数。如果发生错误，返回值可能小于计数。
以下程序说明了上述功能:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate fread() function
#include <bits/stdc++.h>
#include <cstdio>
using namespace std;

int main()
{
    FILE* file_;
    char buffer[100];
    file_ = fopen("g4g.txt", "aman");
    while (!feof(file_)) // to read file
    {
        // function used to read the contents of file
        fread(buffer, sizeof(buffer), 1, file_);
        cout << buffer;
    }
    return 0;
}
```