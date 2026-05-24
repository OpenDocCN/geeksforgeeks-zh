# 使用 C# 中的 If-else 和 Switch 语句获取一个月的总天数

> 原文:[https://www . geeksforgeeks . org/get-每月使用 if-else-and-switch-statement-in-c-sharp/](https://www.geeksforgeeks.org/getting-the-total-number-of-days-in-a-month-using-if-else-and-switch-statements-in-c-sharp/)

给定一个数字 **N** ，任务是写一个 C# 程序来 p 打印月中的天数 **N** 。

**示例:**

> ***输入:**N = 12*
> T5**输出:** 31
> 
> ***输入:** N = 2*
> ***输出:** 28/29*

这项任务可以通过以下方法完成:

**1。** [**使用 else** **语句****:**](https://www.geeksforgeeks.org/c-sharp-decision-making-else-else-ladder-nested-switch-nested-switch/# ifelse)**适当的月号被勾选然后一个月中的天数被打印使用 else if 语句。天数如下:**

```cs
Month = [1, 3, 5, 7, 8, 10, 12] , Number of days = 31
Month = [2] , Number of days = 28/29
Month = [4, 6, 9, 11] , Number of days = 30 
```

**以下是上述方法的实现:**

****输出:****

## **C#**

```cs
// C# Program to Print Number of Days
// in a Month using Else If Statement

using System;

public class GFG{

    // Function to print the Number
    // of Days in a N
    static void PrintNumberofDays(int N) 
    {
       // Check for the Ns
        if (N == 1 || N == 3 || N == 5 || N == 7
          || N == 8 || N == 10 || N == 12) {
              Console.Write("31");
        } 

        else if (N == 4 || N == 6 || N == 9 ||
               N == 11) {
               Console.Write("30");
        } 

        else if (N == 2) {
               Console.Write("28/29");
        }
    }

    // Driver Code
    static public void Main ()
    {
        int N = 5; // 1 <= N <= 12
        PrintNumberofDays(N);
    }
}
```

****输出:****

```cs
31 
```

****2。使用切换条件** **:** 同 Else if，这里勾选月号，重定向到病例，然后打印一个月的天数。 下面是上述方法的实现:**

## **C#**

```cs
// C# Program to Print Number of Days
// in a Month using Switch Condition

using System;

public class GFG{

    // Function to print the Number
    // of Days in a N
    static void PrintNumberofDays(int N) 
    {
        // Check for the N
        switch(N )
        {
            case 1:
            case 3:
            case 5:     
            case 7:
            case 8:
            case 10:
            case 12:             
                Console.Write("31");
                break;

            case 4: 
            case 6:
            case 9:
            case 11:                 
                Console.Write("30"); 
                break;

            case 2:
            Console.Write("28/29");
            break;
        }
    }

    // Driver Code
    static public void Main ()
    {
        int N = 5; // 1 <= N <= 12
        PrintNumberofDays(N);
    }
}
```

****输出:****

```cs
31 
```