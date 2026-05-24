# 将一个文本文件的内容附加到另一个文本文件的 C++ 程序

> 原文:[https://www . geesforgeks . org/CPP-program-to-append-content-of-one-text-file-to-other/](https://www.geeksforgeeks.org/cpp-program-to-append-content-of-one-text-file-to-another/)

给定源和目标文本文件。将内容从源文件追加到目标文件，然后显示目标文件的内容。

**示例:**

```cpp
Input : file.txt : "geeks", file2.txt : "geeks for"
Output: file2.txt : "geeks for geeks"

```

**方式:**
**1)** 在 inputstream 中打开 **file.txt** ，在 outputstream 中打开 **file2.txt** 带追加选项，不删除文件之前的内容。
**2)** 检查打开或定位文件时是否有错误。如果是，则抛出一条错误消息。
**3)** 如果两个文件都找到了，那么将内容从源文件写到目标文件。
**4)** 显示目的文件的内容。

```cpp
// C++ implementation to append
// content from source file to
// destination file
#include <bits/stdc++.h>
using namespace std;

// driver code
int main()
{
    fstream file;

    // Input stream class to
    // operate on files.
    ifstream ifile("file.txt", ios::in);

    // Output stream class to
    // operate on files.
    ofstream ofile("file2.txt", ios::out | ios::app);

    // check if file exists
    if (!ifile.is_open()) {

        // file not found (i.e, not opened).
        // Print an error message.
        cout << "file not found";
    }
    else {
        // then add more lines to
        // the file if need be
        ofile << ifile.rdbuf();
    }
    string word;

    // opening file
    file.open("file2.txt");

    // extracting words form the file
    while (file >> word) {

        // displaying content of
        // destination file
        cout << word << " ";
    }

    return 0;
}
```

输出:

```cpp
geeks for geeks

```