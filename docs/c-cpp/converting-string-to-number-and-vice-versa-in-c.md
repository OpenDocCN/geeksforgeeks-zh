# 在 C++ 中将字符串转换为数字，反之亦然

> 原文:[https://www . geesforgeks . org/converting-string-to-number-反之亦然-in-c/](https://www.geeksforgeeks.org/converting-string-to-number-and-vice-versa-in-c/)

一般来说，或者更具体地说，在竞争性编程中，有很多情况下我们需要将一个数字转换成一个字符串，或者将字符串转换成一个数字。但是由于缺乏对某些基本工具的了解，我们不得不这样做。本文中提到了实现这一任务的一些方法。

**<u>将字符串转换为数字</u>**

**方法 1** :使用 stringstream 类或 sscanf()
**方法 2** :使用 stoi()或 atoi()
进行字符串转换这两种方法在[这篇](https://www.geeksforgeeks.org/converting-strings-numbers-cc/)文章中已经详细讨论过了。
**方法三:使用 boost 词法转换**
Boost 库提供了一个内置函数“词法转换(词法转换)”(“字符串”)，直接将字符串转换为数字。如果输入无效，它会返回一个异常“bad _ 词法 _cast”。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
//C++ code to demonstrate working of lexical_cast()
#include<iostream>
#include <boost/lexical_cast.hpp>// for lexical_cast()
#include <string> // for string
using namespace std;
int main()
{
   string str = "5";
   string str1 = "6.5";

   // Initializing f_value with casted float
   // f_value is 6.5
   float f_value = boost::lexical_cast<float>(str1);

   // Initializing i_value with casted int
   // i_value is 5
   int i_value = boost::lexical_cast<int>(str);

   //Displaying casted values
   cout << "The float value after casting is : ";
   cout << f_value <<endl;
   cout << "The int value after casting is : ";
   cout << i_value <<endl;

   return 0;
}
```

输出:

```cpp
The float value after casting is : 6.5
The int value after casting is : 5
```

**<u>将数字转换为字符串</u>**

**方法 1:使用字符串流**
在该方法中，字符串流声明一个流对象，该对象首先将一个数字作为流插入到一个对象中，然后使用“str()”跟随数字到字符串的内部转换。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate string stream method
// to convert number to string.
#include<iostream>
#include <sstream>  // for string streams
#include <string>  // for string
using namespace std;
int main()
{
    int num = 2016;

    // declaring output string stream
    ostringstream str1;

    // Sending a number as a stream into output
    // string
    str1 << num;

    // the str() converts number into string
    string geek = str1.str();

    // Displaying the string
    cout << "The newly formed string from number is : ";
    cout << geek << endl;

    return 0;
}
```

输出:

```cpp
The newly formed string from number is : 2016
```

**方法 2:使用 to_string()**
这个函数接受一个数字(可以是任何数据类型)并返回所需字符串中的数字。
**实施:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate "to_string()" method
// to convert number to string.
#include<iostream>
#include<string> // for string and to_string()
using namespace std;
int main()
{
    // Declaring integer
    int i_val = 20;

    // Declaring float
    float f_val = 30.50;

    // Conversion of int into string using
    // to_string()
    string stri = to_string(i_val);

    // Conversion of float into string using
    // to_string()
    string strf = to_string(f_val);

    // Displaying the converted strings
    cout << "The integer in string is : ";
    cout << stri << endl;
    cout << "The float in string is : ";
    cout << strf << endl;

    return 0;   
}
```

输出:

```cpp
The integer in string is : 20
The float in string is : 30.500000
```

**方法 3:使用 boost 词法转换**
类似于字符串转换，“词法转换()”函数保持不变，但这次参数列表修改为“词法转换(numeric_var)”。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate "lexical_cast()" method
// to convert number to string.
#include <boost/lexical_cast.hpp> // for lexical_cast()
#include <string> // for string
using namespace std;
int main()
{ 
   // Declaring float
   float f_val = 10.5;

   // Declaring int
   int i_val = 17;

   // lexical_cast() converts a float into string
   string strf = boost::lexical_cast<string>(f_val);

   // lexical_cast() converts a int into string
   string stri = boost::lexical_cast<string>(i_val);

   // Displaying string converted numbers
   cout << "The float value in string is : ";
   cout << strf << endl;
   cout << "The int value in string is : ";
   cout << stri << endl;

   return 0;  
}
```

输出:

```cpp
The float value in string is : 10.5
The int value in string is : 17
```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。