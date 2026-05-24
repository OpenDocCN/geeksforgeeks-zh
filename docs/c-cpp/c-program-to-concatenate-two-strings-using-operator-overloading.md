# 使用运算符重载

连接两个字符串的 C++ 程序

> 原文:[https://www . geesforgeks . org/c-program-to-concatenate-two-string-use-operator-overloading/](https://www.geeksforgeeks.org/c-program-to-concatenate-two-strings-using-operator-overloading/)

**先决条件:**[c++ 中的运算符重载](https://www.geeksforgeeks.org/types-of-operator-overloading-in-c/)
给定两个字符串。任务是在 C++ 中使用运算符重载来连接这两个字符串。

**示例:**

```cpp
Input: str1 = "hello", str2 = "world"
Output: helloworld

Input: str1 = "Geeks", str2 = "World"
Output: GeeksWorld
```

**方法 1** :使用一元运算符重载。

*   使用一元运算符重载连接两个字符串。用两个字符串变量声明一个类。
*   创建类的实例，并调用该类的参数化构造函数，用主函数的输入字符串初始化这两个字符串变量。
*   重载一元运算符![+  ](img/47acf37fe84c4cb27fc7a8b69add4080.png "Rendered by QuickLaTeX.com")来连接类实例的这两个字符串变量。
*   最后，调用运算符函数并连接两个类变量。

下面是上述方法的实现:

## C++

```cpp
// C++ Program to concatenate two string
// using unary operator overloading
#include <iostream>
#include <string.h>

using namespace std;

// Class to implement operator overloading
// function for concatenating the strings
class AddString {

public:
    // Classes object of string
    char s1[25], s2[25];

    // Parameterized Constructor
    AddString(char str1[], char str2[])
    {
        // Initialize the string to class object
        strcpy(this->s1, str1);
        strcpy(this->s2, str2);
    }

    // Overload Operator+ to concat the string
    void operator+()
    {
        cout << "\nConcatenation: " << strcat(s1, s2);
    }
};

// Driver Code
int main()
{
    // Declaring two strings
    char str1[] = "Geeks";
    char str2[] = "ForGeeks";

    // Declaring and initializing the class
    // with above two strings
    AddString a1(str1, str2);

    // Call operator function
    +a1;
    return 0;
}
```

**Output:** 

```cpp
Concatenation: GeeksForGeeks
```

**方法 2:** 使用二进制运算符重载。

*   用字符串变量和运算符函数“+”声明一个类，该运算符函数接受该类的一个实例，并将其变量与当前实例的字符串变量连接起来。
*   创建类的两个实例，并分别用两个输入字符串初始化它们的类变量。
*   现在，使用重载运算符(+)函数来连接两个实例的类变量。

下面是上述方法的实现:

## C++

```cpp
// C++ Program to concatenate two strings using
// binary operator overloading
#include <iostream>
#include <string.h>

using namespace std;

// Class to implement operator overloading function
// for concatenating the strings
class AddString {

public:
    // Class object of string
    char str[100];

    // No Parameter Constructor
    AddString() {}

    // Parameterized constructor to
    // initialize class Variable
    AddString(char str[])
    {
        strcpy(this->str, str);
    }

    // Overload Operator+ to concatenate the strings
    AddString operator+(AddString& S2)
    {
        // Object to return the copy
        // of concatenation
        AddString S3;

        // Use strcat() to concat two specified string
        strcat(this->str, S2.str);

        // Copy the string to string to be return
        strcpy(S3.str, this->str);

        // return the object
        return S3;
    }
};

// Driver Code
int main()
{
    // Declaring two strings
    char str1[] = "Geeks";
    char str2[] = "ForGeeks";

    // Declaring and initializing the class
    // with above two strings
    AddString a1(str1);
    AddString a2(str2);
    AddString a3;

    // Call the operator function
    a3 = a1 + a2;
    cout << "Concatenation: " << a3.str;

    return 0;
}
```

**Output:** 

```cpp
Concatenation: GeeksForGeeks
```