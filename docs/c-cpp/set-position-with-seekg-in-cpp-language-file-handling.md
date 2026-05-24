# 在 C++ 语言文件处理中用 seekg()设置位置

> 原文:[https://www . geesforgeks . org/set-position-with-seekg-in-CPP-language-file-handling/](https://www.geeksforgeeks.org/set-position-with-seekg-in-cpp-language-file-handling/)

seekg()是 iostream 库中的一个函数(标准库的一部分)，它允许您查找文件中的任意位置。它在文件处理中用于设置要从给定文件的输入流中提取的下一个字符的位置。例如:

```cpp
Input : "Hello World" 
Output : World

```

**语法–**文件处理中 seekg()有两种语法:

1.  istream&seekg(streampos 位置)；
2.  istream&seekg(streamoff 偏移量，IOs _ base::seekdir dir)；

**描述–**

*   **位置:**是流缓冲区中的新位置。
*   **偏移量:**是 streamoff 类型的整数值，表示流缓冲区中的偏移量。它是相对于 dir 参数的。
*   **dir :** 为寻找方向。它是 ios_base::seekdir 类型的对象，可以采用以下任何常量值。

偏移值有 3 个方向:

*   ios_base::beg(从流缓冲区开始的偏移量)。
*   ios_base::cur(流缓冲区中当前位置的偏移量)。
*   ios_base::end(从流缓冲区的末尾开始的偏移量)。

**代码–**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Code to demonstrate the seekg function in file handling
#include <fstream>
#include <iostream>

using namespace std;

int main (int argc, char** argv)
{
    // Open a new file for input/output operations
    // discarding any current in the file (assumes
    // a length of zero on opening)
    fstream myFile("test.txt", ios::in | ios::out | ios::trunc);

    // Add the characters "Hello World" to the file
    myFile << "Hello World";

    // Seek to 6 characters from the beginning of the file
    myFile.seekg(6, ios::beg);

    // Read the next 5 characters from the file into a buffer
    char A[6];
    myFile.read(A, 5);

    // End the buffer with a null terminating character
    A[5] = 0;

    // Output the contents read from the file and close it
    cout << A << endl;

    myFile.close();
}
```

**输出–**

```cpp
World

```

**注意–**
如果我们之前在流中得到一个文件结尾，seekg 不会重置它，但是在很多实现中会返回一个错误。–使用 clear()方法首先清除文件结尾位。这是一个相对常见的错误，如果 seekg()的表现不如预期。
本文由**希瓦尼·巴盖尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。