# 使用运算符重载比较两个字符串的 C++ 程序

> 原文:[https://www . geesforgeks . org/c-程序-比较-两个字符串-使用-运算符-重载/](https://www.geeksforgeeks.org/c-program-to-compare-two-strings-using-operator-overloading/)

**先决条件:**[c++ 中的运算符重载](https://www.geeksforgeeks.org/operator-overloading-c/)
给定两个字符串，如何使用运算符重载检查这两个字符串是否相等。

**示例:**

```cpp
Input: ABCD, XYZ
Output: ABCD is not equal to XYZ
        ABCD is greater than XYZ

Input: Geeks, Geeks
Output: Geeks is equal to Geeks
```

**方法:**使用二进制运算符重载。

*   用字符串变量和运算符函数“==”、“<=’ and ‘> =”声明一个类，该类接受该类的一个实例，并将其变量与当前实例的字符串变量进行比较。
*   创建类的两个实例，并分别用两个输入字符串初始化它们的类变量。
*   现在，使用重载运算符(==，<= and > =)函数来比较两个实例的类变量。

下面是上述方法的实现:

## C++

```cpp
// C++ program to compare two Strings
// using Operator Overloading

#include <cstring>
#include <iostream>
#include <string.h>

using namespace std;

// Class to implement operator overloading
// function for concatenating the strings
class CompareString {

public:
    // Classes object of string
    char str[25];

    // Parameterized Constructor
    CompareString(char str1[])
    {
        // Initialize the string to class object
        strcpy(this->str, str1);
    }

    // Overloading '==' under a function
    // which returns integer 1/true
    // if left operand string
    // and right operand string are equal.
    //(else return 0/false)
    int operator==(CompareString s2)
    {
        if (strcmp(str, s2.str) == 0)
            return 1;
        else
            return 0;
    }

    // Overloading '<=' under a function
    // which returns integer 1/true
    // if left operand string is smaller than
    // or equal to the right operand string.
    // (else return 0/false)
    int operator<=(CompareString s3)
    {
        if (strlen(str) <= strlen(s3.str))
            return 1;
        else
            return 0;
    }

    // Overloading '>=' under a function
    // which returns integer 1/true
    // if left operand string is larger than
    // or equal to the right operand string.
    //(else return 0/false)
    int operator>=(CompareString s3)
    {
        if (strlen(str) >= strlen(s3.str))
            return 1;
        else
            return 0;
    }
};

void compare(CompareString s1, CompareString s2)
{

    if (s1 == s2)
        cout << s1.str << " is equal to "
             << s2.str << endl;
    else {
        cout << s1.str << " is not equal to "
             << s2.str << endl;
        if (s1 >= s2)
            cout << s1.str << " is greater than "
                 << s2.str << endl;
        else
            cout << s2.str << " is greater than "
                 << s1.str << endl;
    }
}

// Testcase1
void testcase1()
{
    // Declaring two strings
    char str1[] = "Geeks";
    char str2[] = "ForGeeks";

    // Declaring and initializing the class
    // with above two strings
    CompareString s1(str1);
    CompareString s2(str2);

    cout << "Comparing \"" << s1.str << "\" and \""
         << s2.str << "\"" << endl;

    compare(s1, s2);
}

// Testcase2
void testcase2()
{
    // Declaring two strings
    char str1[] = "Geeks";
    char str2[] = "Geeks";

    // Declaring and initializing the class
    // with above two strings
    CompareString s1(str1);
    CompareString s2(str2);

    cout << "\n\nComparing \"" << s1.str << "\" and \""
         << s2.str << "\"" << endl;

    compare(s1, s2);
}

// Driver code
int main()
{
    testcase1();
    testcase2();

    return 0;
}
```

**Output:** 

```cpp
Comparing "Geeks" and "ForGeeks"
Geeks is not equal to ForGeeks
ForGeeks is greater than Geeks

Comparing "Geeks" and "Geeks"
Geeks is equal to Geeks
```