# 如何从现有文本文件创建二进制文件？

> 原文:[https://www . geesforgeks . org/如何从现有文本文件中创建二进制文件/](https://www.geeksforgeeks.org/how-to-create-binary-file-from-the-existing-text-file/)

在本文中，我们将讨论如何从给定的文本文件创建二进制文件。在继续这些步骤之前，让我们先介绍一下什么是文本文件和二进制文件。

[**文本文件**](https://www.geeksforgeeks.org/c-program-to-create-a-file/) **:** 文本文件以人类可读的形式顺序存储数据。

[**二进制文件**](https://www.geeksforgeeks.org/cpp-program-to-modify-the-content-of-a-binary-file/) **:** 二进制文件以位/位组(字节)的形式按顺序存储数据。这些位的组合可以引用自定义数据。二进制文件可以存储多种类型的数据，如图像、音频、文本等。

**问题陈述:**这里的任务是从文本文件中读取数据，并创建一个新的二进制文件，其中包含二进制形式的相同数据。

**示例:**假设在名为**“cust data . txt”**的文件中有客户的详细信息，任务是通过从文本文件**“cust data . txt”**中读取数据来创建名为**“Customerdb”**的二进制文件。

*   文件**“cust data . txt”**的每一行都包含一个客户信息的记录。
*   一条记录有 3 个属性，即 **ID** 、**姓名**和**年龄**。
*   每条记录都有固定的长度。

让我们假设**“cust data . txt”**有以下数据-

<figure class="table">T15T18】AnnilT23T26】RamT28】45T31

| 身份证明 | name | age |
| --- | --- | --- |
| one | Twenty-two | Two |

</figure>

*   让记录大小，一条**记录中的字节数= B** 。
*   如果将 **3 个客户**的数据写入磁盘文件，那么该文件将包含 **3 × B 字节**。
*   如果文件中有客户记录相对位置**“pos”**的信息，那么可以直接读取客户的信息。
*   **位置*(B–1)**将是记录的起始字节位置。

因此，没有要求以文本格式存储记录中的所有值。内部格式可用于直接存储值。一个好的可以作为选择的选项是定义一个 [*结构*](https://www.geeksforgeeks.org/structures-c/) 供我们记录。

```cpp
struct Customers 
{
    int ID;
    char name[30];
    int age;
}
```

现在可以通过创建结构变量 cs 来访问结构客户的各个元素，如下所示:

1.  cs.ID。
2.  cs.name。
3.  cs.age。

让我们看看读取文本文件和写入二进制文件所需的方法。读取所需的功能是 [fscanf()](https://www.geeksforgeeks.org/scanf-and-fscanf-in-c-simple-yet-poweful/) ，写入所需的功能是 [fwrite()](https://www.geeksforgeeks.org/fwrite-vs-write/) 。

**读取:**[**fscanf()**](https://www.geeksforgeeks.org/scanf-and-fscanf-in-c-simple-yet-poweful/)**功能用于读取包含客户数据的文本文件。**

****语法:****

> ****int fscanf(FILE* streamPtr，const char* formatPtr，…)；**
> 该函数从文件流中读取数据，并将值存储到相应的变量中。**

****fscanf()参数:****

*   ****streamPtr:** 它指定了指向要从中读取数据的输入文件流的[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)。**
*   ****formatPtr:** 指向空终止字符串的指针，该字符串指定如何读取输入。它由以%开头的格式说明符组成。**示例:** %d 代表 int、%s 代表 string 等。**

**使用此[功能](https://www.geeksforgeeks.org/functions-in-c/)需要包含 <cstdio>[头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)。</cstdio>**

****写入:**[**fwrite()**](https://www.geeksforgeeks.org/readwrite-structure-file-c/)**功能是在程序中将从文本文件读取的数据以二进制形式写入二进制文件。****

******语法:******

> ******size _ t fwrite(const void * bufPtr，size size size，size_t count，FILE * ptr _ output stream)；**
> fwrite()函数将“计数”对象的数量写入给定的输出流，其中每个对象的大小是“大小”字节。****

******write()参数:******

*   ******bufPtr:** 指向其内容被写入的内存块的指针(转换为**常量** void*)。****
*   ******大小:**每个要写入的对象的字节大小。****
*   ******计数:**要读取的对象总数。****
*   ******ptr_OutputStream:** 指向指定要写入的输出文件流的文件的指针。****

****使用该功能需要包含<cstdio>头文件。</cstdio>****

******算法:**下面是程序读取文本文件并将二进制形式的内容写入二进制文件的方法。****

*   ****打开输入文本文件和输出二进制文件。****
*   ****在到达文本文件末尾之前，请执行以下步骤:

    *   从输入文本文件中读取一行，使用 **fscanf()** 分成 3 个变量。
    *   结构变量被设置为元素的值(将结构变量写入输出文件。
    *   使用 **fwrite()** 将该结构变量写入输出二进制文件。**** 
*   ****关闭输入文本文件和输出二进制文件。****

****以下是上述方法的 [C++ 程序](https://www.geeksforgeeks.org/c-plus-plus/):****

## ****C++****

```cpp
**// C++ program for the above approach
#include <cstdio>
#include <cstring>
#include <iostream>
using namespace std;

// Creating a structure for customers
struct Customers {
    int ID;
    char name[30];
    int age;
};

// Driver Code
int main()
{
    struct Customers cs;
    int rec_size;
    rec_size = sizeof(struct Customers);
    cout << "Size of record is: "
         << rec_size << endl;

    // Create File Pointers fp_input for
    // text file, fp_output for output
    // binary file
    FILE *fp_input, *fp_output;

    // Open input text file, output
    // binary file.
    // If we cannot open them, work
    // cannot be done, so return -1
    fp_input = fopen("custdata.txt", "r");

    if (fp_input == NULL) {
        cout << "Could not open input file"
             << endl;
        return -1;
    }

    fp_output = fopen("Customerdb", "wb");

    if (fp_output == NULL) {
        cout << "Could not open "
             << "output file" << endl;
        return -1;
    }

    // Read one line from input text file,
    // into 3 variables id, n & a
    int id, a;
    char n[30];

    // Count for keeping count of total
    // Customers Records
    int count = 0;
    cout << endl;

    // Read next line from input text
    // file until EOF is reached
    while (!feof(fp_input)) {

        // Reading the text file
        fscanf(fp_input, "%d %s %d ",
               &id, n, &a);

        // Increment the count by one
        // after reading a record
        count++ ;

        // Structure variable cs is set
        // to values to elements
        cs.ID = id, strcpy(cs.name, n), cs.age = a;

        // Write the structure variable
        // cs to output file
        fwrite(&cs, rec_size, 1, fp_output);
        printf(
            "Customer number %2d has"
            " data %5d %30s %3d \n",
            count, cs.ID,
            cs.name, cs.age);
    }

    cout << "Data  from file read"
         << " and printed\n";
    cout << "Database created for "
         << "Customers info\n";

    // Count contains count of total records
    cout << "Total records written: "
         << count << endl;

    // Close both the files
    fclose(fp_input);
    fclose(fp_output);

    return 0;
}**
```

******输出:******

```cpp
**Size of record is: 40

Customer number  1 has data     1                    Annil  22
Customer number  2 has data     2                      Ram  45
Customer number  3 has data     3                    Golu  25          
Data  from file read and printed
Database created for Customers info     
Total records written: 3**
```

******说明:**文件“custdata.txt”中有 3 条记录以二进制方式被读取、打印并保存在“Customerdb”文件中。
文本文件每行包含 3 个字段——身份证、姓名和年龄。
文本文件的第一行包含-****

```cpp
 **1                    Annil  22**
```

****从文件中读取这一行，即读取 id、Name 和 Age 的数据，并将它们的值分别分配给变量 ID、n 和 a。现在将这 3 个变量的值分别分配给数据成员:结构变量 cs 的 ID、名称[]和年龄。
现在使用 **fwrite( & cs，rec_size，1，fp_output)** ，将一个 rec_size 大小的 cs 对象写入二进制文件-“FP _ output”(二进制模式)。
该过程对文本文件的所有行继续，直到到达文件的末尾。程序执行结束后，文件“custdata.txt”将保持原样，就像在读取模式下打开的一样-****

```cpp
 **1                         Annil  22
 2                           Ram  45
 3                          Golu  25**
```

****该数据被逐行读取，并以二进制模式写入文件“Customerdb”。文件“Customerdb”将包含二进制形式的内容，这是不可读的。正常打开时，文件如下所示:****

****![](img/cd219c16374e5c9e55702a2a7a1c0041.png)****