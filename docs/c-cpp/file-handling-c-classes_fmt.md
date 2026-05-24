# 通过 C++ 类进行文件处理

> 原文:[https://www.geeksforgeeks.org/file-handling-c-classes/](https://www.geeksforgeeks.org/file-handling-c-classes/)

在 C++ 中，文件主要通过使用 `fstream` headerfile 中可用的三个类 `fstream`、`ifstream`、`ofstream` 来处理。
**`ofstream`:** Stream 类写入文件
**`ifstream`:** Stream 类读取文件
**`fstream`:** Stream 类读取/写入文件。

![](img/6b4ef70b42e3939b088543f2cbeb330e.png)

现在第一步是打开特定文件进行读或写操作。我们可以通过：
1. 对象创建时在构造函数中传递文件名。
2. 使用 `open()` 方法。

**例如**

> **使用构造函数**
> `ifstream` 打开文件(`const char* filename`, `ios_base::openmode mode = ios_base::in`);
> `ifstream fin(filename, openmode)` 默认为 `openmode = ios::in`
> `ifstream fin("filename")`;
>
> **使用打开方法**
> 打开文件，调用默认构造函数
> `ifstream fin`;
> `fin.open(filename, openmode)`
> `fin.open("filename")`;

**模式:**

| Member constant | represent | visit |
| --- | --- | --- |
| `in` | input | File open reading: the internal stream buffer supports input operation. |
| `out` | output | File open for writing: the internal stream buffer supports output operation. |
| `binary` | binary system | The operation is in binary mode instead of text mode. |
| `ate` |  | The output position starts at the end of the file. |
| `app` | add to | All output operations of occur at the end of the file and are appended to its existing contents. |
| `trunc` | cut off | Anything that existed before the file was opened will be discarded. |

**默认打开模式:**

| 类 | 默认模式 |
| --- | --- |
| `ofstream` | `ios::out` |
| `ifstream` | `ios::in` |
| `fstream` | `ios::in | ios::out` |

**问题陈述**: 用 C++ 读写文件。
**例:**

```cpp
Input : 
Welcome in GeeksforGeeks. Best way to learn things.

Output : 
Welcome in GeeksforGeeks. Best way to learn things.
```

下面是使用流类的 `ifstream` & `ofstream` 实现。

## 使用 ifstream 和 ofstream

```cpp
/* File Handling with C++ using ifstream & ofstream class object*/
/* To write the Content in File*/
/* Then to read the content of file*/
#include <iostream>

/* fstream header file for ifstream, ofstream,
  fstream classes */
#include <fstream>

using namespace std;

// Driver Code
int main()
{
    // Creation of ofstream class object
    ofstream fout;

    string line;

    // by default ios::out mode, automatically deletes
    // the content of file. To append the content, open in ios::app
    // fout.open("sample.txt", ios::app)
    fout.open("sample.txt");

    // Execute a loop If file successfully opened
    while (fout) {

        // Read a Line from standard input
        getline(cin, line);

        // Press -1 to exit
        if (line == "-1")
            break;

        // Write line in file
        fout << line << endl;
    }

    // Close the File
    fout.close();

    // Creation of ifstream class object to read the file
    ifstream fin;

    // by default open mode = ios::in mode
    fin.open("sample.txt");

    // Execute a loop until EOF (End of File)
    while (fin) {

        // Read a Line from File
        getline(fin, line);

        // Print line in Console
        cout << line << endl;
    }

    // Close the file
    fin.close();

    return 0;
}
```

下面是使用 `fstream` 类的实现。

## 使用 fstream

```cpp
/* File Handling with C++ using fstream class object */
/* To write the Content in File */
/* Then to read the content of file*/
#include <iostream>

/* fstream header file for ifstream, ofstream,
   fstream classes */
#include <fstream>

using namespace std;

// Driver Code
int main()
{
    // Creation of fstream class object
    fstream fio;

    string line;

    // by default openmode = ios::in|ios::out mode
    // Automatically overwrites the content of file, To append
    // the content, open in ios::app
    // fio.open("sample.txt", ios::in|ios::out|ios::app)
    // ios::trunc mode delete all content before open
    fio.open("sample.txt", ios::trunc | ios::out | ios::in);

    // Execute a loop If file successfully Opened
    while (fio) {

        // Read a Line from standard input
        getline(cin, line);

        // Press -1 to exit
        if (line == "-1")
            break;

        // Write line in file
        fio << line << endl;
    }

    // Execute a loop until EOF (End of File)
    // point read pointer at beginning of file
    fio.seekg(0, ios::beg);

    while (fio) {

        // Read a Line from File
        getline(fio, line);

        // Print line in Console
        cout << line << endl;
    }

    // Close the file
    fio.close();

    return 0;
}
```