# C 程序统计一串元音和辅音的个数

> 原文:[https://www . geesforgeks . org/c-program-to-count-number-of-in-a-string-元音和辅音/](https://www.geeksforgeeks.org/c-program-to-count-number-of-vowels-and-consonants-in-a-string/)

给定一个字符串，编写一个 C 程序来计算这个字符串中元音和辅音的数量。

**示例:**

```cpp
Input: str = "geeks for geeks"
Output:
Vowels: 5
Consonants: 8

Input: str = "abcdefghijklmnopqrstuvwxyz"
Output:
Vowels: 5
Consonants: 21

```

**进场:**

*   以[字符串为输入](https://www.geeksforgeeks.org/taking-string-input-space-c-3-different-methods/)
*   从这个字符串中取出每个字符进行检查
*   如果这个字符是元音，增加元音的数量
*   否则增加辅音的数量。
*   最后打印元音和辅音的总数。

下面是上述方法的实现:

```cpp
// C program to count the number of
// vowels and consonants in a string

#include <stdio.h>

// Function to count number
// of vowels and consonant
void count_vowels_and_consonant(char* str)
{
    // Declare the variable vowels and consonant
    int vowels = 0, consonants = 0;

    int i;
    char ch;

    // Take each character from this string to check
    for (i = 0; str[i] != '\0'; i++) {

        ch = str[i];

        // If this character is a vowel,
        // increment the count of vowels
        if (ch == 'a' || ch == 'e'
            || ch == 'i' || ch == 'o'
            || ch == 'u' || ch == 'A'
            || ch == 'E' || ch == 'I'
            || ch == 'O' || ch == 'U')
            vowels++ ;

        // If this character is a space
        // skip it
        else if (ch == ' ')
            continue;

        else
            // Else increment the count of consonants
            consonants++ ;
    }

    // Print the total count of vowels and consonants
    printf("\nVowels: %d", vowels);
    printf("\nConsonants: %d", consonants);
}

// Driver function.
int main()
{
    char* str = "geeks for geeks";
    printf("String: %s", str);

    count_vowels_and_consonant(str);

    return 0;
}
```

**Output:**

```cpp
String: geeks for geeks
Vowels: 5
Consonants: 8

```