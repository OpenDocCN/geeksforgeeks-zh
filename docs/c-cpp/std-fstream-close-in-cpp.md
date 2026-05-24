# std::fstream::close()在 C++ 中

> 原文:[https://www.geeksforgeeks.org/std-fstream-close-in-cpp/](https://www.geeksforgeeks.org/std-fstream-close-in-cpp/)

[文件](https://www.geeksforgeeks.org/basics-file-handling-c/)在编程中起着重要的作用。它允许永久存储数据。 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 语言提供了一种机制，将程序的输出存储在文件中，并从磁盘上的文件进行浏览。这种机制被称为[文件处理](https://www.geeksforgeeks.org/file-handling-c-classes/)。为了执行文件处理，使用的一些常规功能如下:

*   [**【打开()】**](https://www.geeksforgeeks.org/input-output-system-calls-c-create-open-close-read-write/)【T4:】该功能帮助创建文件，并以不同模式打开文件，如输入操作、输出操作、二进制模式等。
*   [**关闭()**](https://www.geeksforgeeks.org/file-handling-c-classes/) **:此功能有助于关闭已有文件。**
*   **get():** 这个函数有助于从文件中读取单个字符。
*   **put()** :这个功能有助于在文件中写入单个字符。
*   [**read()**](https://www.geeksforgeeks.org/how-to-work-with-file-handling-in-c/) **:此功能有助于从文件中读取数据。**
*   [**write()**](https://www.geeksforgeeks.org/readwrite-class-objects-fromto-file-c/) **:这个功能帮助我们将数据写入文件。**

一个[流](https://www.geeksforgeeks.org/c-stream-classes-structure/)是一个[抽象](https://www.geeksforgeeks.org/abstraction-in-c/)，它代表一个工具，在这个工具上执行输入和输出操作。根据使用情况，流通常被表示为不定长度字符的来源或目的地。到目前为止，[头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)提供功能**【CIN】**和 **cout** 分别用于要求控制台输入和写入控制台输出。在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中有一组文件处理方法。这些包括 [ifstream、ofstream 和 fsstream](https://www.geeksforgeeks.org/file-handling-c-classes/)。这些类是从**fsstream base**和相应的 iostream 类获得的。这些类被设计成能够管理在 fstream 中声明的磁盘文件，因此这个文件必须包含在任何使用文件的程序中。

**fsstream Library:**fsstream 是一个由两者组成的库， **ofstream** 和 **ifstream** 这意味着它可以创建文件，向文件写入信息，以及从文件中读取信息。该头文件一般用作[数据类型](https://www.geeksforgeeks.org/c-data-types/)，表示[文件流](https://www.geeksforgeeks.org/io-redirection-c/)。用于描述打开、读取、输入和关闭文件等的语法。

**如何关闭文件？**为了使用磁盘文件存储数据，需要确定文件及其预期用途的以下参数。需要注意的参数如下:

*   文件的名称。
*   文件的数据类型和结构。
*   目的(读取、写入数据)。
*   打开方法。
*   使用后关闭文件。

本文的重点是关闭文件。在一种情况下，如果一个 [C++ 程序](https://www.geeksforgeeks.org/c-plus-plus/)终止，那么它会自动清空所有的流，释放所有分配的内存，并关闭所有打开的文件。因此，使用 close()函数关闭与文件相关的流是一个很好的选择，它是 ifsream、ofstream 和 fstream 对象的成员。

**语法:**

```cpp
close()
```

**属性:**

*   **返回值:**close()函数不提供[返回值](https://www.geeksforgeeks.org/how-to-return-multiple-values-from-a-function-in-c-or-cpp/)，这意味着如果操作失败，包括如果在调用之前没有打开文件，则为流设置 failbit 状态标志(如果该状态标志是使用成员异常注册的，则可能引发 IOs _ base::fail。
*   **异常处理:**当函数有异常且流处于有效状态时，那么内部操作抛出的任何异常都会被函数捕获，并在关闭文件后重新抛出。只有当函数失败(设置**故障位**状态标志)并且成员异常被设置为该状态时，它才会引发成员类型故障异常。
*   它修改了**流**对象。对等价流的并发访问可能会引入数据竞争。

下面是 [C++ 程序](https://www.geeksforgeeks.org/c-plus-plus/)实现 close()功能:

## C++

```cpp
// C++ program to implement close() function
#include <fstream>
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    char data[100];

    // Open a file in write
    // mode.
    ofstream outfile;
    outfile.open("gfg.dat");

    cout << "Writing to the file" << endl;
    cout << "Enter your name: ";

    // This function will take the entire
    // the user enters and will store in
    // the "data" array declare above
    cin.getline(data, 100);

    // Write inputted data into
    // the file.
    outfile << data << endl;

    // Here we make use of the close()
    // function to close the opened file
    outfile.close();

    // Open a file in read mode
    ifstream infile;
    infile.open("gfg.dat");

    cout << "Reading from the file"
         << endl;
    infile >> data;

    // Write the data at the screen
    cout << data << endl;

    // Close the opened file
    infile.close();

    return 0;
}
```

**输出:**

[![](img/22b4d8421e31feeb79d6750a8a46c8d6.png)](https://media.geeksforgeeks.org/wp-content/uploads/20210514171910/sdf.JPG)