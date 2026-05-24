# 编程输入工作日号码，用 C# 打印工作日

> 原文:[https://www . geesforgeks . org/program-to-input-weekday-number-and-print-the-weekday-in-c-sharp/](https://www.geeksforgeeks.org/program-to-input-weekday-number-and-print-the-weekday-in-c-sharp/)

C# 程序打印给定工作日号码(0-6)的工作日名称。一个 **[开关语句](https://www.geeksforgeeks.org/switch-statement-in-c-sharp/)** 允许用一个值或事例列表检查一个值。

工作日号码是数值从 **0 到 6** 的号码。0 代表**“周日”**，1 代表**“周一”**，2 代表**“周二”**，3 代表**“周三”**，4 代表**“周四”**，5 代表**“周五”**，6 代表**“周六”**。这将通过 switch 语句来检查。

**示例:**

```cs
Input: 2

Output: Tuesday

Input: 6

Output: Saturday 

```

**例 1:**

```cs
// C# program to input weekday number 
// print the weekday
using System;
using System.IO;
using System.Text;

namespace Geeks
{
    class GFG
    {
        // Main Method 
        static void Main(string[] args)
        {
            int weekday;

            // input weekday number
            Console.Write("Enter weekday number (0-6): ");
            weekday = Convert.ToInt32(Console.ReadLine());

            // Using switch case to validate
            switch (weekday)
            {
                case 0:
                    Console.WriteLine("It is SUNDAY");
                    break;
                case 1:
                    Console.WriteLine("It is MONDAY");
                    break;
                case 2:
                    Console.WriteLine("It is TUESDAY");
                    break;
                case 3:
                    Console.WriteLine("It is WEDNESDAY");
                    break;
                case 4:
                    Console.WriteLine("It is THURSDAY");
                    break;
                case 5:
                    Console.WriteLine("It is FRIDAY");
                    break;
                case 6:
                    Console.WriteLine("It is SATURDAY");
                    break;

            }

        }
    }
}
```

**输出:**当我们输入(0-6)之间的数字时。

```cs
Enter weekday number (0-6): It is WEDNESDAY
```

**例 2:**

```cs
// C# program to input weekday number 
// print the weekday
using System;
using System.IO;
using System.Text;

namespace Geeks
{
    class GFG
    {
        // Main Method 
        static void Main(string[] args)
        {
            int weekday;

            // input weekday number
            Console.Write("Enter weekday number (0-6): ");
            weekday = Convert.ToInt32(Console.ReadLine());

            // Using switch case to validate
            switch (weekday)
            {
                case 0:
                    Console.WriteLine("It is SUNDAY");
                    break;
                case 1:
                    Console.WriteLine("It is MONDAY");
                    break;
                case 2:
                    Console.WriteLine("It is TUESDAY");
                    break;
                case 3:
                    Console.WriteLine("It is WEDNESDAY");
                    break;
                case 4:
                    Console.WriteLine("It is THURSDAY");
                    break;
                case 5:
                    Console.WriteLine("It is FRIDAY");
                    break;
                case 6:
                    Console.WriteLine("It is SATURDAY");
                    break;

                // if no case value is matched
                default:
                    Console.WriteLine("It is wrong input");
                    break;
            }

        }
    }
}
```

**输出:**当我们输入超出范围(0-6)的数字时。

```cs
Enter weekday number (0-6): It is wrong input
```