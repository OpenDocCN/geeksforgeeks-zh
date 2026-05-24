# 将结构数据类型转换为十六进制字符串，反之亦然

> 原文:[https://www . geesforgeks . org/struct-data-type-conversion-to-hex-string-反之亦然/](https://www.geeksforgeeks.org/conversion-of-struct-data-type-to-hex-string-and-vice-versa/)

系统中产生的**日志文件**大多是**二进制(0，1)** 或**十六进制(0x)** 格式。有时您可能需要将这些数据映射成可读的格式。

将这些十六进制信息转换成系统定义的数据类型，如“int/string/float”相对容易。另一方面，当您有一些用户定义的数据类型，如“struct”时，这个过程可能会很复杂。

以下基本程序将帮助您完成上述操作。在现实世界中实现时，您需要更多的错误处理。

```cpp
// C++ Program to convert a 'struct' in 'hex string'
// and vice versa
#include <iostream>
#include <iomanip>
#include <sstream>
#include <string>

using namespace std;

struct Student_data
{
    int  student_id;
    char name[16];
};

void convert_to_hex_string(ostringstream &op,
                      const unsigned char* data, int size)
{
    // Format flags
    ostream::fmtflags old_flags = op.flags();

    // Fill characters
    char old_fill  = op.fill();
    op << hex << setfill('0');

    for (int i = 0; i < size; i++)
    {
        // Give space between two hex values
        if (i>0)
            op << ' ';

        // force output to use hex version of ascii code
        op << "0x" << setw(2) << static_cast<int>(data[i]);
    }

    op.flags(old_flags);
    op.fill(old_fill);
}

void convert_to_struct(istream& ip, unsigned char* data,
                       int size)
{
    // Get the line we want to process
    string line;
    getline(ip, line);

    istringstream ip_convert(line);
    ip_convert >> hex;

    // Read in unsigned ints, as wrote out hex version
    // of ascii code
    unsigned int u = 0;
    int i = 0;

    while ((ip_convert >> u) && (i < size))
        if((0x00 <= u) && (0xff >= u))
            data[i++ ] = static_cast<unsigned char>(u);
}

// Driver code
int main()
{
    Student_data student1 = {1, "Rohit"};
    ostringstream op;

    // Function call to convert 'struct' into 'hex string'
    convert_to_hex_string(op,
             reinterpret_cast<const unsigned char*>(&student1),
             sizeof(Student_data));

    string output = op.str();
    cout << "After conversion from struct to hex string:\n"
         << output << endl;

    // Get te hex string
    istringstream ip(output);
    Student_data student2 = {0};

    // Function call to convert 'hex string' to 'struct'
    convert_to_struct(ip,
                reinterpret_cast<unsigned char*>(&student2),
                sizeof(Student_data));

    cout << "\nAfter Conversion form hex to struct: \n";
    cout << "Id \t: " << student2.student_id << endl;
    cout << "Name \t: "<< student2.name << endl;

    return 0;
}
```

输出:

```cpp
After conversion from struct to hex string:
0x01 0x00 0x00 0x00 0x52 0x6f 0x68 0x69 0x74 0x00 0x00 0x00 0x00 0x00 
0x00 0x00 0x00 0x00 0x00 0x00

After Conversion form hex to struct: 
Id 	: 1
Name 	: Rohit

```

本文由**罗希特·卡斯勒**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上述话题的信息，请写评论