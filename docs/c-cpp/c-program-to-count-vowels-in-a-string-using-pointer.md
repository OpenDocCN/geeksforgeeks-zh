# 使用指针

对字符串中的元音进行计数的 C++ 程序

> 原文:[https://www . geesforgeks . org/c-程序-使用指针计数字符串中的元音/](https://www.geeksforgeeks.org/c-program-to-count-vowels-in-a-string-using-pointer/)

**先决条件:**[c++ 中的指针](https://www.geeksforgeeks.org/char-vs-stdstring-vs-char-c/)

给定一串小写英文字母。任务是使用指针计算字符串中元音的数量

**示例:**

```cpp
Input : str = "geeks"
Output : 2

Input : str = "geeksforgeeks"
Output : 5 

```

**进场:**

1.  使用字符数组初始化字符串。
2.  创建一个字符指针，并用字符数组(字符串)中的第一个元素初始化它。
3.  创建一个计数元音的计数器。
4.  循环迭代，直到字符指针找到' \0 '空字符，一旦遇到空字符，就停止循环。
5.  迭代指针时检查是否有元音，如果找到元音，增加计数。
6.  打印计数。

下面是上述方法的实现:

```cpp
// CPP program to print count of
// vowels using pointers

#include <iostream>

using namespace std;

int vowelCount(char *sptr)
{
    // Create a counter
    int count = 0;

    // Iterate the loop until null character encounter
    while ((*sptr) != '\0') {

        // Check whether character pointer finds any vowels
        if (*sptr == 'a' || *sptr == 'e' || *sptr == 'i'
            || *sptr == 'o' || *sptr == 'u') {

            // If vowel found increment the count
            count++ ;
        }

        // Increment the pointer to next location
        // of address
        sptr++ ;
    }

    return count;
}

// Driver Code
int main()
{
    // Initialize the string
    char str[] = "geeksforgeeks";

    // Display the count
    cout << "Vowels in above string: " << vowelCount(str);

    return 0;
}
```

**Output:**

```cpp
Vowels in above string: 5

```