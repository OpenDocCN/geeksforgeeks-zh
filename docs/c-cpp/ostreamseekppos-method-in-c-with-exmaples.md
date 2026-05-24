# c++ 中的 ostream::seekp(pos)方法，示例

> 原文:[https://www . geeksforgeeks . org/ostramsekepps-method-in-c-with-ex maples/](https://www.geeksforgeeks.org/ostreamseekppos-method-in-c-with-exmaples/)

C++ 中 **ostream 的 **seekp(pos)** 方法用于将输出序列中指针的位置设置为指定位置。此方法采用要设置的新位置，并将位置设置为指定新位置的 ostream 实例返回。
**语法:**** 

```cpp
ostream& seekp(streampos pos);
```

**参数:**该方法以待设定的**新位置**为参数。
**返回值:**该方法返回**该牡蛎实例**，位置设置为指定的新位置。
**异常:**如果操作设置了一个内部状态标志(除了 eofbit)注册了成员异常，函数抛出一个成员类型的异常**失败**。
以下示例演示了 seekp()方法在 C++ 中的使用:
**示例 1:** 演示 seekp()在二进制文件
中的使用

*   接受用户关于要显示的记录序列号的输入
*   向函数传递 n，然后以读取模式打开文件
*   通过 **seekp((n-1)*Sizeof(对象))**将写指针放在记录的开始处
*   将记录写入文件，然后关闭它
*   打开文件读取数据，然后关闭文件

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to show the use of
// ostream::seekp() method using binary file

#include <bits/stdc++.h>
using namespace std;

class student {
    int rno;
    char name[20];

public:
    void getdata()
    {
       name = "geek" rno = 11;
    }

    void putdata()
    {
        cout << rno << endl
             << name << endl;
    }

    // accepts the serial number
    // of record to be displayed
    void DisplayRecordAtPosition(int);
};

void student::DisplayRecordAtPosition(int n)
{

    ofstream ofs;

    // opening the file in writing mode
    ofs.open("he.dat", ios::out | ios::binary);

    // displays the size of the object
    // sizeof object is 22
    // char[20]+int = 1*20 + 2 = 22
    cout << "size of record: "
         << sizeof(*this) << endl;

    // Using seekp() method to change position
    ofs.seekp((n - 1) * sizeof(student));

    // Writing in the new position
  ofs.write(char*)this, sizeof(student));

  // Closing the output stream
  ofs.close();

  ifstream ifs;
  ifs.open("he.dat", ios::in | ios::binary);
  ifs.seekg((n - 1) * sizeof(student);
  ifs.read((char*)this, sizeof(student)) ";
  putdata();
  ifs.close();
}

// Driver code
int main()
{
    student s;
    int pos = 1;

    s.getdata();

    cout << "record no " << pos
         << " (position int file "
         << pos - 1 << ")\n";
    s.DisplayRecordAtPosition(pos);

    return 0;
}
```

**输出:**

```cpp
size of record: 24
record no 1 (position int file 0)
rno: 1
name: geek
```