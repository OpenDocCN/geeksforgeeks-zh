# 从文件中删除给定行号的行的程序

> 原文:[https://www . geesforgeks . org/program-delete-line-given-line-number-file/](https://www.geeksforgeeks.org/program-delete-line-given-line-number-file/)

给定一个文件和一个行号 n，任务是从给定的文本文件中删除第 n <sup>行</sup>行。
假设 **myfile.txt** 的初始内容为:

```cpp
GeeksforGeeks
GeeksforGeeks IDE
GeeksforGeeks Practice
GeeksforGeeks Contribute

```

删除**第 2 行**后，内容为:

```cpp
GeeksforGeeks
GeeksforGeeks IDE
GeeksforGeeks Contribute

```

**进场:**
**1)** 以输入方式打开源文件，逐字符读取。
**2)** 在输出模式下打开另一个文件，并将内容逐个字符地放入文件中。
**3)** 将另一个文件重命名为源文件。

```cpp
// C++ Program to delete the given
// line number from a file
#include <bits/stdc++.h>
using namespace std;

// Delete n-th line from given file
void delete_line(const char *file_name, int n)
{
    // open file in read mode or in mode
    ifstream is(file_name);

    // open file in write mode or out mode
    ofstream ofs;
    ofs.open("temp.txt", ofstream::out);

    // loop getting single characters
    char c;
    int line_no = 1;
    while (is.get(c))
    {
        // if a newline character
        if (c == '\n')
        line_no++ ;

        // file content not to be deleted
        if (line_no != n)
            ofs << c;
    }

    // closing output file
    ofs.close();

    // closing input file
    is.close();

    // remove the original file
    remove(file_name);

    // rename the file
    rename("temp.txt", file_name);
}

// Driver code
int main()
{
    int n = 3;
    delete_line("a.txt", n);
    return 0;
}
```

```cpp
 Note: Run this code offline IDE keep text file name 
as "a.txt" in same folder 
```