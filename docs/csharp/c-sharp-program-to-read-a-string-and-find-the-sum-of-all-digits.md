# C# 程序读取字符串并求所有数字的和

> 原文:[https://www . geesforgeks . org/c-sharp-程序读取字符串并查找所有数字的总和/](https://www.geeksforgeeks.org/c-sharp-program-to-read-a-string-and-find-the-sum-of-all-digits/)

给定一个字符串，我们的任务是首先从用户那里读取这个字符串，然后找到给定字符串中所有数字的总和。

**示例**

```cs
Input : abc23d4
Output: 9

Input : 2a3hd5j
Output: 10
```

**方法:**

> 要读取字符串并找到字符串中所有数字的总和，请遵循以下步骤:
> 
> *   First, we use the console to read strings from users. The ReadLine () method.
> *   Initializes an integer sum with a value of 0.
> *   Now iterate over the string until the end.
> *   If the character value is greater than or equal to "0" and less than or equal to "9" (that is, the ascii value is between 48 and 57), the ***character-"0"*** (which gives the character value) is executed and added to the sum.
> *   Sum now contains the sum value of all the numbers in the string.

**例:**

## c#

```cs
// C# program to read the string from the user and
// then find the sum of all digits in the string
using System;

class GFG{

public static void Main()
{
    string str;
    Console.WriteLine("Enter a string ");

    // Reading the string from user.
    str = Console.ReadLine();
    int count, sum = 0;
    int n = str.Length;

    for(count = 0; count < n; count++)
    {

        // Checking if the string contains digits or not
        // If yes then add the numbers to find their sum 
        if ((str[count] >= '0') && (str[count] <= '9'))
        {
            sum += (str[count] - '0');
        }
    }
    Console.WriteLine("Sum = " + sum);
}
}
```

#### 产出 1:

```cs
Enter a string
abc23d4
Sum = 9
```

**输出 2:**

```cs
Enter a string
2a3hd5j
Sum = 10
```

**说明:**在上面的例子中，首先我们读取字符串，我们将迭代每个字符，并通过比较字符的 ASCII 值来检查该字符是否为整数。如果字符是整数，则将该值加到总和中。迭代结束时，sum 变量将包含字符串中数字的总和。