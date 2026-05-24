# 在 C/C++ 中将字符串转换为数字

> 原文:[https://www . geesforgeks . org/converting-strings-numbers-cc/](https://www.geeksforgeeks.org/converting-strings-numbers-cc/)

将字符串转换为数字有两种常用方法:

**使用 stringstream 类或 sscanf()**
**string stream():**这是一种将数字字符串转换为整数、浮点或双精度的简单方法。下面是一个使用 stringstream 将字符串转换为 int 的示例程序。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A program to demonstrate the use of stringstream
#include <iostream>
#include <sstream>
using namespace std;

int main()
{
    string s = "12345";

    // object from the class stringstream
    stringstream geek(s);

    // The object has the value 12345 and stream
    // it to the integer x
    int x = 0;
    geek >> x;

    // Now the variable x holds the value 12345
    cout << "Value of x : " << x;

    return 0;
}
```

输出:

```cpp
Value of x : 12345
```

```cpp
// A stringstream is similar to input/output
// file stream. We need to declare a stringstream
// just like an fstream, for example: 
stringstream ss;

// and, like an fstream or cout, 
// we can write to it:
ss << myString; or 
ss << myCstring; or
ss << myInt;, or float, or double, etc.

// and we can read from it:
ss >> myChar; or
ss >> myCstring; or
ss >> myInt;  
```

总而言之，stringstream 是一种操作字符串的便捷方式。
**sscanf()** 是一个类似于 scanf()的 C 风格函数。它从字符串中读取输入，而不是标准输入。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<stdio.h>
int main()
{
    const char *str = "12345";
    int x;
    sscanf(str, "%d", &x);
    printf("\nThe value of x : %d", x);
    return 0;
}
```

输出:

```cpp
Value of x : 12345
```

同样，我们可以分别使用%f 和%lf 读取 float 和 double。

**使用 stoi()或 atoi()**
**stoi():**stoi()函数将字符串作为参数并返回其值。下面是一个简单的实现:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate working of stoi()
// Work only if compiler supports C++ 11 or above.
#include <iostream>
#include <string>
using namespace std;

int main()
{
    string str1 = "45";
    string str2 = "3.14159";
    string str3 = "31337 geek";

    int myint1 = stoi(str1);
    int myint2 = stoi(str2);
    int myint3 = stoi(str3);

    cout << "stoi(\"" << str1 << "\") is "
         << myint1 << '\n';
    cout << "stoi(\"" << str2 << "\") is "
         << myint2 << '\n';
    cout << "stoi(\"" << str3 << "\") is "
         << myint3 << '\n';

    return 0;
}
```

输出:

```cpp
stoi("45") is 45
stoi("3.14159") is 3
stoi("31337 geek") is 31337 
```

**atoi():**atoi()函数以字符数组或字符串文字作为参数，并返回其值。下面是一个简单的实现:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// For C++ 11 above
#include <cstdlib>
#include <iostream>
using namespace std;

int main()
{
    const char* str1 = "42";
    const char* str2 = "3.14159";
    const char* str3 = "31337 geek";

    int num1 = atoi(str1);
    int num2 = atoi(str2);
    int num3 = atoi(str3);

    cout << "atoi(\"" << str1 << "\") is " << num1 << '\n';
    cout << "atoi(\"" << str2 << "\") is " << num2 << '\n';
    cout << "atoi(\"" << str3 << "\") is " << num3 << '\n';

    return 0;

}
```

## C

```cpp
#include <stdio.h>
#include <stdlib.h>
int main()
{

    char* str1 = "42";
    char* str2 = "3.14159";
    char* str3 = "31337 geek";

    int myint1 = atoi(str1);
    int myint2 = atoi(str2);
    int myint3 = atoi(str3);

    printf("stoi(%s) is %d \n", str1, myint1);
    printf("stoi(%s) is %d \n", str2, myint2);
    printf("stoi(%s) is %d \n", str3, myint3);

    // This Code is Contributed by Harshit Srivastava
    return 0;
}
```

输出:

```cpp
atoi("42") is 42
atoi("3.14159") is 3
atoi("31337 geek") is 31337 
```

**stoi()对 atoi()**

*   atoi()是一个遗留的 C 风格函数。stoi()是在 C++ 11 中添加的。

*   atoi()只适用于 C 风格的字符串(字符数组和字符串文字)，stoi()适用于 C++ 字符串和 C 风格的字符串
*   atoi()只接受一个参数并返回整数值。

```cpp
int atoi (const char * str); 
```

*   stoi()最多可接受三个参数，第二个参数用于起始索引，第三个参数用于输入数字的基数。

```cpp
int stoi (const string&  str, size_t* index = 0, int base = 10); 
```

**练习**
编写自己的 atof()，它以一个字符串(表示浮点值)作为参数，并将其值作为双精度返回。
**参考:**
[http://www.cplusplus.com/reference/string/stoi/](http://www.cplusplus.com/reference/string/stoi/)
[http://www.cplusplus.com/reference/sstream/stringstream/](http://www.cplusplus.com/reference/sstream/stringstream/)
[http://www.cplusplus.com/reference/cstdlib/atoi/](http://www.cplusplus.com/reference/cstdlib/atoi/)
本文由**西弗·辛格**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。