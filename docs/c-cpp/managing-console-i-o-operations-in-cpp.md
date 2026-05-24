# 在 C++ 中管理控制台输入/输出操作

> 原文:[https://www . geesforgeks . org/management-console-I-o-operations-in-CPP/](https://www.geeksforgeeks.org/managing-console-i-o-operations-in-cpp/)

每个程序都将一些数据作为输入，并按照熟悉的输入过程输出周期生成经过处理的数据作为输出。了解如何提供输入数据并以所需的形式呈现结果是至关重要的。[使用 **cin** 和 **cout**](https://www.geeksforgeeks.org/cincout-vs-scanfprintf/) 已经与[运算符 **> >和 **< <****](https://www.geeksforgeeks.org/overloading-stream-insertion-operators-c/) 一起用于[输入和输出操作](https://www.geeksforgeeks.org/unformatted-input-output-operations-in-cpp/)。在本文中，我们将讨论如何控制输出的打印方式。

[C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 支持丰富的 [I/O 功能](https://www.geeksforgeeks.org/formatted-i-o-in-c/)和操作。这些函数使用了 C++ 的高级[特性，如](https://www.geeksforgeeks.org/features-of-c/)[类](https://www.geeksforgeeks.org/c-classes-and-objects/)、[派生类](https://www.geeksforgeeks.org/difference-between-base-class-and-derived-class-in-c/)、[虚函数](https://www.geeksforgeeks.org/virtual-function-cpp/)。它还支持 C 的所有 I/O 函数集，因此可以在 C++ 程序中使用，但是由于两个原因，它们的使用应该受到限制。C++ 中的

1.  I/O method supports OOPS of [concept.](https://www.geeksforgeeks.org/object-oriented-programming-in-cpp/)
2.  I/O methods in [T0】 C 【T1] can't handle user-defined data types, such as [class and object](https://www.geeksforgeeks.org/c-classes-and-objects/) .

它使用[流和流类](https://www.geeksforgeeks.org/c-stream-classes-structure/)的概念，用控制台和磁盘文件实现其输入/输出操作。

### <u>C++ 流</u>

C++ 中的[输入/输出系统设计用于各种设备，包括终端、磁盘和磁带机。尽管每个设备都非常不同，但输入/输出系统为程序员提供了一个独立于被访问的实际设备的接口。这个界面被称为](https://www.geeksforgeeks.org/basic-input-output-c/)[**流**](https://www.geeksforgeeks.org/c-stream-classes-structure/) **。**

*   流是字节序列。
*   向程序提供数据的源流称为输入流。
*   从程序接收输出的目标流称为输出流。
*   输入流中的数据可以来自键盘或任何其他输入设备。
*   输出流中的数据可以进入屏幕或任何其他输出设备。

C++ 包含几个预定义的流，当程序开始执行时，这些流会自动打开。其中包括 **cin** 和 **cout** 。已知 **cin** 代表连接到标准输入设备(通常是键盘)的输入流， **cout** 代表连接到标准输出设备(通常是屏幕)的输出流。

### **<u>C++ 流类</u>**

[C++ 输入/输出系统](https://www.geeksforgeeks.org/basic-input-output-c/)包含一个类的层次结构，用于定义各种流来处理控制台和磁盘文件。这些类称为流类。用于输入和输出操作的流类的层次结构在控制台单元中。这些类在**头文件 iostream** 中声明。该文件应包含在与控制台单元通信的所有程序中。

## c++

```cpp
#include <iostream>
using namespace std;

int main()
{

    cout << " This is my first"
            " Blog on the gfg";
    return 0;
}
```

**输出:**

```cpp
This is my first Blog on the gfg

```

**ios** 是 **istream** (输入流)和 **ostream** (输出流)的基类，而后者又是**I stream**(输入/输出流)的基类。类 **ios** 被声明为[虚拟基类](https://www.geeksforgeeks.org/virtual-base-class-in-c/)，因此 iostream 只继承其成员的一个[副本。](https://www.geeksforgeeks.org/are-array-members-deeply-copied/)

类 **ios** 为[格式化和非格式化输入/输出操作](https://www.geeksforgeeks.org/formatted-i-o-in-c/)提供基本支持。类 istream 提供格式化和非格式化输入的工具，而类 ostream(通过继承)提供格式化输出的工具。

iostream 类提供了处理输入和输出流的工具。三个类给这些类添加一个赋值:

*   **是 s tream _ with assign**

**ostream _ with assign**
*   **iostream _ with assign**

#### **<u>控制台操作流类的表格表示</u> :**

<figure class="table">

| 

### Category name

 | 

### 内容

 |
| --- | --- |
| 

#### 通用输入/输出流类

 | 

*   Contains the basic facilities used by all other input and output classes.
*   It also contains a pointer to the buffer object ( **streambuf** object).
*   Declare constants and functions necessary for processing formatted input and output operations.

 |
| 

#### 输入流

 | 

*   It inherits **iOS**
*   Attribute, which declares input functions such as [**get (), getline (), and read ()**](https://www.geeksforgeeks.org/getline-string-c/)
*   It contains overloaded extraction operators **> >**

 |
| 

#### 输出流

 | 

*   It inherits the attributes of **IOs** .
*   Declare input functions such as [**put ()**](https://www.geeksforgeeks.org/puts-vs-printf-for-printing-a-string/) [**write ()**](https://www.geeksforgeeks.org/readwrite-class-objects-fromto-file-c/) .
*   It contains a [overload extraction operator](https://www.geeksforgeeks.org/overloading-stream-insertion-operators-c/) **< <** .

 |
| 

#### 输入/输出流

 | 

*   The attributes of **iOS streams** and **Ostream** are inherited through multiple inheritance, thus including all input and output functions.

 |
| 

#### stream buf

 | 

*   It provides an interface for physical devices through buffers.
*   It serves as the basis of the ios files used by the filebuf class.

 |

</figure>