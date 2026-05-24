# getline()函数和字符数组

> 原文:[https://www . geesforgeks . org/getline-function-character-array/](https://www.geeksforgeeks.org/getline-function-character-array/)

先决条件:[C++ 中的 getline(string)](https://www.geeksforgeeks.org/getline-string-c/)
在 c++ 中，流类支持面向行的函数，getline()和 write()分别执行输入和输出函数。getline()函数读取以新行结束的整行文本，或者直到达到最大限制。getline()是 istream 类的成员函数，语法如下:

```cpp
// (buffer, stream_size, delimiter)
istream& getline(char*, int size, char='\n')

// The delimiter character is considered as '\n'
istream& getline(char*, int size)

```

该函数执行以下操作:
1。提取直到分隔符的字符。
2。将字符存储在缓冲区中。
3。提取的最大字符数为大小–1。
*注意，终止符(或定界符)字符可以是任何字符(如' '、'、'或任何特殊字符等)。).终止符被读取，但没有保存到缓冲区中，取而代之的是空字符*。

```cpp
// C++ program to show the getline() with 
// character array
#include <iostream>
using namespace std;

int main()
{
    char str[20];
    cout << "Enter Your Name::";

    // see the use of getline() with array
    // str also replace the above statement
    // by cin >> str and see the difference
    // in output
    cin.getline(str, 20);

    cout << "\nYour Name is:: " << str;
    return 0;
}
```

输入:

```cpp
Aditya Rakhecha 
```

输出:

```cpp
 Your Name is:: Aditya Rakhecha

```

在上面的程序中，语句 cin.getline(str，20)读取一个字符串，直到它遇到新的行字符或最大字符数(这里是 20)。尝试不同极限的函数，看输出。