# STD::c++ 中的字符串类

> 原文:[https://www.geeksforgeeks.org/stdstring-class-in-c/](https://www.geeksforgeeks.org/stdstring-class-in-c/)

在其定义中，C++ 有一种方式将**字符序列表示为类**的对象。这个类叫做 std:: string。String 类将字符存储为字节序列，其功能是允许**访问单字节字符**。

**标准::字符串对字符数组**

*   字符数组只是字符的**数组**可以以空字符结束。字符串是一个**类，它定义了表示为字符流的对象**。

*   字符数组的大小必须**静态分配**，如果需要，在运行时不能分配更多的内存。在字符数组的情况下，未使用的已分配**内存被浪费**。如果是字符串，内存是**动态分配的**。可以在运行时按需分配更多内存。由于没有预分配内存，**没有浪费内存**。

*   有**威胁的** [**阵衰的**](https://www.geeksforgeeks.org/what-is-array-decay-in-c-how-can-it-be-prevented/) 以防字符阵。由于字符串被表示为对象，**不会发生数组衰减**。

*   **字符数组的实现比 std:: string 更快**。**字符串在实现上比字符数组慢**。

*   字符数组**不提供**太多**内置功能**来操纵字符串。字符串类定义了**多个允许对字符串进行多种操作的功能**。

**琴弦操作**

**输入功能**
**1。getline()** :-该功能用于将用户输入的字符流存储在对象存储器中。
**2。push_back()** :-该功能用于**在字符串的**端**输入**一个字符。
**3。pop_back()** :-从 C++ 11 引入(针对字符串)，此功能用于**删除字符串中最后一个字符**。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// getline(), push_back() and pop_back()
#include<iostream>
#include<string> // for string class
using namespace std;
int main()
{
    // Declaring string
    string str;

    // Taking string input using getline()
    // "geeksforgeek" in giving output
    getline(cin,str);

    // Displaying string
    cout << "The initial string is : ";
    cout << str << endl;

    // Using push_back() to insert a character
    // at end
    // pushes 's' in this case
    str.push_back('s');

    // Displaying string
    cout << "The string after push_back operation is : ";
    cout << str << endl;

    // Using pop_back() to delete a character
    // from end
    // pops 's' in this case
    str.pop_back();

    // Displaying string
    cout << "The string after pop_back operation is : ";
    cout << str << endl;

    return 0;

}
```

输入:

```cpp
geeksforgeek
```

输出:

```cpp
The initial string is : geeksforgeek
The string after push_back operation is : geeksforgeeks
The string after pop_back operation is : geeksforgeek
```

**【容量功能】**
**4。capacity()** :-该功能**返回分配给字符串的容量**，该容量可以是等于或大于字符串大小的**。分配额外的空间，以便当新字符被添加到字符串中时，**操作可以有效地完成**。
**5。resize()** :-此功能**改变字符串**的大小，大小可以增减。
**6 . length()**:-此函数**求字符串的长度**
**7 . shrink _ to _ fit()**:-此函数**减小字符串的容量**，使其等于字符串的最小容量。如果我们确定不需要进一步添加字符，该操作对于节省额外的内存**是有用的。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// capacity(), resize() and shrink_to_fit()
#include<iostream>
#include<string> // for string class
using namespace std;
int main()
{
    // Initializing string
    string str = "geeksforgeeks is for geeks";

    // Displaying string
    cout << "The initial string is : ";
    cout << str << endl;

    // Resizing string using resize()
    str.resize(13);

    // Displaying string
    cout << "The string after resize operation is : ";
    cout << str << endl;

    // Displaying capacity of string
    cout << "The capacity of string is : ";
    cout << str.capacity() << endl;

    //Displaying length of the string
    cout<<"The length of the string is :"<<str.length()<<endl;

    // Decreasing the capacity of string
    // using shrink_to_fit()
    str.shrink_to_fit();

    // Displaying string
    cout << "The new capacity after shrinking is : ";
    cout << str.capacity() << endl;

    return 0;

}
```

**Output**

```cpp
The initial string is : geeksforgeeks is for geeks
The string after resize operation is : geeksforgeeks
The capacity of string is : 26
The length of the string is :13
The new capacity after shrinking is : 15

```

**迭代器函数**
**8。begin()** :-这个函数返回一个**迭代器**到字符串的**开头**。
**9。end()** :-该函数返回一个**迭代器**到字符串的 **end** 。
**10。rbegin()** :-这个函数返回一个**反向迭代器**指向字符串的**端**。
**11。rend()** :-这个函数返回一个**反向迭代器**，指向字符串的**开头**。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// begin(), end(), rbegin(), rend()
#include<iostream>
#include<string> // for string class
using namespace std;
int main()
{
    // Initializing string`
    string str = "geeksforgeeks";

    // Declaring iterator
    std::string::iterator it;

    // Declaring reverse iterator
    std::string::reverse_iterator it1;

    // Displaying string
    cout << "The string using forward iterators is : ";
    for (it=str.begin(); it!=str.end(); it++)
    cout << *it;
    cout << endl;

    // Displaying reverse string
    cout << "The reverse string using reverse iterators is : ";
    for (it1=str.rbegin(); it1!=str.rend(); it1++)
    cout << *it1;
    cout << endl;

    return 0;

}
```

**Output**

```cpp
The string using forward iterators is : geeksforgeeks
The reverse string using reverse iterators is : skeegrofskeeg

```

**【操纵功能】**
**12。复制(“char 数组”，len，pos)** :-此函数**复制其参数中提到的目标字符数组**中的子串。需要 3 个参数，**目标字符数组，需要复制的长度和字符串中的起始位置才能开始复制。**
**13。swap()** :-此功能**将一个字符串与另一个字符串交换**。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// copy() and swap()
#include<iostream>
#include<string> // for string class
using namespace std;
int main()
{
    // Initializing 1st string
    string str1 = "geeksforgeeks is for geeks";

    // Declaring 2nd string
    string str2 = "geeksforgeeks rocks";

    // Declaring character array
    char ch[80];

    // using copy() to copy elements into char array
    // copies "geeksforgeeks"
    str1.copy(ch,13,0);

    // Displaying char array
    cout << "The new copied character array is : ";
    cout << ch << endl << endl;

    // Displaying strings before swapping
    cout << "The 1st string before swapping is : ";
    cout << str1 << endl;
    cout << "The 2nd string before swapping is : ";
    cout << str2 << endl;

    // using swap() to swap string content
    str1.swap(str2);

    // Displaying strings after swapping
    cout << "The 1st string after swapping is : ";
    cout << str1 << endl;
    cout << "The 2nd string after swapping is : ";
    cout << str2 << endl;

    return 0;

}
```

输出:

```cpp
The new copied character array is : geeksforgeeks

The 1st string before swapping is : geeksforgeeks is for geeks
The 2nd string before swapping is : geeksforgeeks rocks
The 1st string after swapping is : geeksforgeeks rocks
The 2nd string after swapping is : geeksforgeeks is for geeks
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// copy() and swap()
#include<iostream>
#include<string> // for string class
using namespace std;
int main()
{
    // Initializing 1st string
    string str1 = "geeksforgeeks is for geeks";

    // Declaring 2nd string
    string str2 = "geeksforgeeks rocks";

    // Declaring character array
    char ch[80];

    // using copy() to copy elements into char array
    // copies "geeksforgeeks"
    str1.copy(ch,13,0);

    // Displaying char array
    cout << "The new copied character array is : ";
    cout << ch << endl << endl;

    // Displaying strings before swapping
    cout << "The 1st string before swapping is : ";
    cout << str1 << endl;
    cout << "The 2nd string before swapping is : ";
    cout << str2 << endl;

    // using swap() to swap string content
    str1.swap(str2);

    // Displaying strings after swapping
    cout << "The 1st string after swapping is : ";
    cout << str1 << endl;
    cout << "The 2nd string after swapping is : ";
    cout << str2 << endl;

    return 0;

}
```

```cpp
The 2nd string after swapping is : geeksforgeeks is for geeks
```

更多功能:
[C++ 字符串类及其应用](https://www.geeksforgeeks.org/c-string-class-and-its-applications/)
[C++ 字符串类及其应用|集合 2](https://www.geeksforgeeks.org/c-string-class-applications-set-2/)

？list = plqm7 alhxfysg6 gsrme 2 ini4k 8 fph5 qvb
本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。