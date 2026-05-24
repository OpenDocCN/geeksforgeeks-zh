# 用 c++ 处理文件中的 tellp()示例

> 原文:[https://www . geesforgeks . org/tellp-file-handling-CPP-example/](https://www.geeksforgeeks.org/tellp-file-handling-cpp-example/)

**tellp()** 函数用于输出流，并返回指针在流中的当前“放”位置。它没有参数，返回一个成员类型 pos_type 的值，这是一个整数数据类型，表示 put 流指针的当前位置。
**语法:**

```cpp
pos_type tellp();
```

**返回–**当前输出位置指示器成功，否则返回-1。
**例 1–**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// cpp code to get the position at particular
// position using tellp() function
#include <iostream>
#include <fstream>
using namespace std;

int main()
{
    fstream file;

    // open file in read and write mode
    file.open("myfile.txt", ios::out);
    file << "geeksforgeeks";

    // print the position of the pointer in file
    cout << "the current position of pointer is :"
         << file.tellp() << endl;

    // close the open file
    file.close();
}
```

**输出–**

```cpp
the current position of pointer is :-1
```

在上面的代码中，tellp()返回它在文件中指向的当前位置。
**例 2–**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// code to add content at particular position
// using tellp()
#include <fstream>
using namespace std;

int main()
{
    long position;
    fstream file;

    // open the file in read and write mode
    file.open("myfile.txt");

    // write content in the file
    file.write("this is an apple", 16);
    position = file.tellp();

    // set position of pointer using seekp
    file.seekp(position - 7);
    file.write(" sam", 4);
    file.close();
}
```

**输出–**

```cpp
this is a sample
```

这里 tellp()函数返回指针的位置，然后使用 seekp()函数，指针从 n 个位置移回，这里它移回 7 个位置，然后在那个位置插入内容。
本文由**希瓦尼·巴盖尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。