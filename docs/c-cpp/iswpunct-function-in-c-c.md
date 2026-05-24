# isw point()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/iswpunct-function-in-c-c/](https://www.geeksforgeeks.org/iswpunct-function-in-c-c/)

**isw point()**是 C/C++ 中的一个函数，用于测试**宽字符代码**是否表示程序当前区域中的类**点**的字符。如果宽字符是标点宽字符代码，则返回非零值，否则返回 0。该功能在**cwcytpe**头文件中定义。该功能检查 **ch** 是否为标点符号。标点符号如下

```cpp
! " # $ % & ' () * +, - . / : ;  ? @ [\] ^ _ ` {|} ~
```

**语法:**

```cpp
int iswpunct(ch)
```

**参数:**该函数接受一个指定要检查的字符的强制参数 ***ch*** 。

**返回值:**如果字符 ch 是标点符号，函数返回非零值，否则返回零。

下面的程序说明了上面的功能:

## C++

```cpp
// C++ program to illustrate
// the iswpunct() function
#include <iostream>
using namespace std;

int main()
{
    int i = 0;
    int count_ = 0;

    // string declaration
    char string1[] = "~Hello geekforgeeks !";
    char string2[count_];

    // iterate in the string
    while (string1[i]) {

        // check if the character is
        // punctuation mark or not
        if (iswpunct(string1[i])) {

            // store the punctuation characters
            string2[count_] = string1[i];
            count_++ ;
        }
        i++ ;
    }

    // prints the punctuation character
    cout <<"The sentence contains" <<  count_ <<"punct. character :\n";
    for (int i = 0; i < count_; i++)
        cout <<" "<< string2[i];
    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C++ program to illustrate
// the iswpunct() function
#include <stdio.h>
int main()
{
    int i = 0;
    int count_ = 0;

    // string declaration
    char string1[] = "~Hello geekforgeeks !";
    char string2[count_];

    // iterate in the string
    while (string1[i]) {

        // check if the character is
        // punctuation mark or not
        if (iswpunct(string1[i])) {

            // store the punctuation characters
            string2[count_] = string1[i];
            count_++ ;
        }
        i++ ;
    }
    // prints the punctuation character
    printf("The sentence contains %d punct. character :\n", count_);
    for (int i = 0; i < count_; i++)
        printf("%c ", string2[i]);
    return 0;
}
```

**Output:** 

```cpp
The sentence contains 2 punct. character :
~ !
```

**程序 2 :**

## C++

```cpp
// C++ program to illustrate
// the iswpunct() function
#include <iostream>
using namespace std;

int main()
{
    int i = 0;
    int count_ = 0;

    // string declaration
    char string1[] = "@#$^gfg";
    char string2[count_];

    // iterate in the string
    while (string1[i]) {

        // check if the character is
        // punctuation mark or not
        if (iswpunct(string1[i])) {

            // store the punctuation characters
            string2[count_] = string1[i];
            count_++ ;
        }
        i++ ;
    }

    // prints the punctuation character
    cout <<"The sentence contains " << count_ << "punct. character :\n";
    for (int i = 0; i < count_; i++)
        cout <<" "<< string2[i];
    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C++ program to illustrate
// the iswpunct() function
#include <bits/stdc++.h>
int main()
{
    int i = 0;
    int count_ = 0;

    // string declaration
    char string1[] = "@#$^gfg";
    char string2[count_];

    // iterate in the string
    while (string1[i]) {

        // check if the character is
        // punctuation mark or not
        if (iswpunct(string1[i])) {

            // store the punctuation characters
            string2[count_] = string1[i];
            count_++ ;
        }
        i++ ;
    }
    // prints the punctuation character
    printf("The sentence contains %d punct. character :\n", count_);
    for (int i = 0; i < count_; i++)
        printf("%c ", string2[i]);
    return 0;
}
```

**Output:** 

```cpp
The sentence contains 4 punct. character :
@ # $ ^
```