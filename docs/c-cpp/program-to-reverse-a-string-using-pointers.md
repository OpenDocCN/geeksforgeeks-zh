# 使用指针反转字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-reverse-a-string-use-pointers/](https://www.geeksforgeeks.org/program-to-reverse-a-string-using-pointers/)

给定一个字符串，任务是使用指针反转这个字符串。

**示例:**

```cpp
Input: Geeks
Output: skeeG

Input: GeeksForGeeks
Output: skeeGroFskeeG

```

**方法:**这个方法包括取两个指针，一个指向字符串的开头，另一个指向字符串的结尾。然后在这两个指针的帮助下，字符一个接一个地反转。

**程序:**

```cpp
#include <stdio.h>
#include <string.h>

// Function to reverse the string
// using pointers
void reverseString(char* str)
{
    int l, i;
    char *begin_ptr, *end_ptr, ch;

    // Get the length of the string
    l = strlen(str);

    // Set the begin_ptr and end_ptr
    // initially to start of string
    begin_ptr = str;
    end_ptr = str;

    // Move the end_ptr to the last character
    for (i = 0; i < l - 1; i++)
        end_ptr++ ;

    // Swap the char from start and end
    // index using begin_ptr and end_ptr
    for (i = 0; i < l / 2; i++) {

        // swap character
        ch = *end_ptr;
        *end_ptr = *begin_ptr;
        *begin_ptr = ch;

        // update pointers positions
        begin_ptr++ ;
        end_ptr--;
    }
}

// Driver code
int main()
{

    // Get the string
    char str[100] = "GeeksForGeeks";
    printf("Enter a string: %s\n", str);

    // Reverse the string
    reverseString(str);

    // Print the result
    printf("Reverse of the string: %s\n", str);

    return 0;
}
```

**Output:**

```cpp
Enter a string: GeeksForGeeks
Reverse of the string: skeeGroFskeeG

```