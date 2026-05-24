# 计算给定字符串中元音和辅音数量的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-count-number-to-number-number-to-number-to-number-to-number-to-number-to-number-to-number-to-number-to-number-to-number-to-number-number-to-number](https://www.geeksforgeeks.org/c-sharp-program-to-count-number-of-vowels-and-consonants-in-a-given-string/)

C# 是一种通用编程语言，用于创建移动应用程序、桌面应用程序、网站和游戏。因为我们知道 a、e、I、o、u 是元音，剩下的字母表在英语中被称为辅音，所以现在使用 C# 语言，我们将创建一个程序，该程序将返回给定字符串中存在的元音和辅音的总数。

**示例:**

```cs
Input: geeksforgeeks
Output: Total number of vowels = 5
Total number of consonants = 8

Input: HelloGFG
Output: Total number of vowels = 2
Total number of consonants = 6
```

**进场:**

> 要打印给定字符串中元音和辅音的总数，我们使用以下方法:
> 
> *   使用字符串数据类型存储字符串。
> *   声明两个变量来计算元音和辅音的数量。
> *   现在使用 length 属性找到给定字符串的长度
> *   现在从左到右迭代字符串，检查字符是元音还是辅音。
> *   如果遇到的字符是元音，增加元音的数量，否则增加辅音的数量。

**例 1:**

## C#

```cs
// C# program to print the total number of Vowels
// and consonants from a given string
using System;  
class GFG{  

public static void Main() 
{
    string inputstring;
    int i, len, vowels, consonants;

    inputstring = "geeksforgeeks";        
    vowels = 0;
    consonants = 0;
    len = inputstring.Length;

    // Iterating the string from left to right
    for(i = 0; i < len; i++)
    {

        // Check if the charator is a vowel
        if (inputstring[i] == 'a' || inputstring[i] == 'e' || 
            inputstring[i] == 'i' || inputstring[i] == 'o' || 
            inputstring[i] == 'u' || inputstring[i] == 'A' || 
            inputstring[i] == 'E' || inputstring[i] == 'I' || 
            inputstring[i] == 'O' || inputstring[i] == 'U')
        {

            // Increment the vowels
            vowels++;
        }

        // Check if the character is a alphabet
        // other than vowels
        else if ((inputstring[i] >= 'a' && inputstring[i] <= 'z') || 
                 (inputstring[i] >= 'A' && inputstring[i] <= 'Z'))
        {

            // Increment the consonants
            consonants++;
        }
    }

    // Display the count of vowels and consonant
    Console.WriteLine("count of vowel = " + vowels);
    Console.WriteLine("count of consonant = " + consonants);
}
}
```

**Output**

```cs
count of vowel = 5
count of consonant = 8
```

**例 2:**

## C#

```cs
// C# program to print the total number of Vowels
// and consonants from a given string
using System;  
class GFG{  

public static void Main() 
{
    char[] inputstring = new char[100];
    int i, vowels, consonants, x;

    vowels = 0;
    consonants = 0;

    // Enter the length of the string
    Console.WriteLine("Please enter the length of the string:\n");
    x = int.Parse(Console.ReadLine());

    // Enter the string
    Console.WriteLine("Enter string:\n");
    for (i = 0; i < x; i++)
    {
        inputstring[i] = Convert.ToChar(Console.Read());
    }

    // Iterating the string 
    for (i = 0; inputstring[i] != '\0'; i++)
    {   

        // Check if the charator is a vowel
        if (inputstring[i] == 'a' || inputstring[i] == 'e' || 
            inputstring[i] == 'i' || inputstring[i] == 'o' || 
            inputstring[i] == 'u' || inputstring[i] == 'A' || 
            inputstring[i] == 'E' || inputstring[i] == 'I' || 
            inputstring[i] == 'O' || inputstring[i] == 'U')
        {

            // Increment the vowels
            vowels++;
        }

        else
        {

            // Increment the consonants
            consonants++;
        }
    }

    // Display the count of vowels and consonant
    Console.WriteLine("\ncount of vowel = " + vowels);
    Console.WriteLine("count of consonant = " + consonants);

    Console.ReadLine();
    Console.ReadLine();
}
}
```

**输出:**

```cs
Please enter the length of the string:
6
Enter string:
HeyGFG
count of vowel = 1
count of consonant = 5
```