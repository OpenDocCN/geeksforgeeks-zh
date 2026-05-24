# C# 程序读取字符串并求所有数字的和

> 原文: [https://www.geeksforgeeks.org/c-sharp-program-to-read-a-string-and-find-the-sum-of-all-digits/](https://www.geeksforgeeks.org/c-sharp-program-to-read-a-string-and-find-the-sum-of-all-digits/)

给定一个字符串，我们的任务是首先从用户那里读取这个字符串，然后找到给定字符串中所有数字的总和。

## 示例

```cs
Input : abc23d4
Output: 9

Input : 2a3hd5j
Output: 10
```

## 方法

要读取字符串并找到字符串中所有数字的总和，请遵循以下步骤:

*   首先，我们使用控制台从用户那里读取字符串。`ReadLine()` 方法。
*   初始化一个整数 `sum`，值为 0。
*   现在遍历字符串直到末尾。
*   如果字符值大于等于 `"0"` 且小于等于 `"9"`（即 ASCII 值在 48 到 57 之间），则执行 `字符 - '0'`（这会得到字符的数值）并将其加到 `sum` 中。
*   `sum` 现在包含了字符串中所有数字的总和值。

## 示例代码

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

### 输出 1

```cs
Enter a string
abc23d4
Sum = 9
```

### 输出 2

```cs
Enter a string
2a3hd5j
Sum = 10
```

## 说明

在上面的例子中，首先我们读取字符串，我们将迭代每个字符，并通过比较字符的 ASCII 值来检查该字符是否为整数。如果字符是整数，则将该值加到总和中。迭代结束时，`sum` 变量将包含字符串中数字的总和。