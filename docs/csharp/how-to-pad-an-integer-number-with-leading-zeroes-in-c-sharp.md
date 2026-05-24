# 如何在 C# 中用前导零填充整数？

> 原文:[https://www . geesforgeks . org/如何在 c-sharp 中用前导零填充整数/](https://www.geeksforgeeks.org/how-to-pad-an-integer-number-with-leading-zeroes-in-c-sharp/)

给定一个**数字 N** ，任务是用 C# 中的 **P** 前导零的数字填充这个数字。

**示例:**

```cs
Input: N = 123 , P = 4
Output: 0123

Input: N = -3 , P = 5
Output: -00003

```

**方法 1:使用字符串 Format()方法****:****Format()**方法用于将指定字符串中的一个或多个格式项替换为指定对象的字符串表示形式 。

> **第一步:**得到数字 N 和的前导零个数 p
> 
> **第二步:**将数字转换为字符串， 垫字符串，使用字符串。Format()方法与 的格式化字符串参数“{0:0000}”为 P= 4。
> 
> ```cs
> val = string.Format("{0:0000}", N);
> 
> ```
> 
> **第三步:**退回补好的绳子。

**示例:**

## C#

```cs
// C# program to pad an integer
// number with leading zeros
using System;

class GFG{

    // Function to pad an integer number 
    // with leading zeros
    static string pad_an_int(int N, int P)
    {
        // string used in Format() method
        string s = "{0:";
        for( int i=0 ; i<P ; i++)
        {
            s += "0";
        }
        s += "}";

        // use of string.Format() method
        string value = string.Format(s, N);

        // return output
        return value;
    }

    // driver code
    public static void Main(string[] args)
    {
        int N = 123; // Number to be pad
        int P = 5; // Number of leading zeros

        Console.WriteLine("Before Padding: " + N);

        // Function calling
        Console.WriteLine("After Padding: " + pad_an_int(N, P));
    }
}
```

**输出:**

```cs
Before Padding: 123
After Padding: 00123

```

**方法 2:使用**[**ToString**](https://www.geeksforgeeks.org/c-sharp-int64-tostring-method-set-1/)**()方法** **:** 使用**ToString****()**方法将当前实例的数值转换为其等价的字符串表示。

> **第一步:**得到数字 N 和的前导零个数 p
> 
> **第 2 步:**使用[ToString()](https://www.geeksforgeeks.org/c-sharp-int64-tostring-method-set-1/)方法将数字转换为字符串，并使用带格式的字符串参数“0000”填充字符串，表示 P= 4。
> 
> ```cs
> val = N.ToString("0000");
> 
> ```
> 
> **第三步:**退回补好的绳子。

**示例:**

## C#

```cs
// C# program to pad an integer
// number with leading zeros
using System;

public class GFG{

    // Function to pad an integer number 
    // with leading zeros
    static string pad_an_int(int N, int P)
    {
        // string used in ToString() method
        string s = "";
        for( int i=0 ; i<P ; i++)
        {
            s += "0";
        }

        // use of ToString() method
        string value = N.ToString(s);

        // return output
        return value;
    }

    // driver code
    public static void Main(string[] args)
    {
        int N = 123; // Number to be pad
        int P = 5; // Number of leading zeros

        Console.WriteLine("Before Padding: " + N);

        // Function calling
        Console.WriteLine("After Padding: " + pad_an_int(N, P));
    }
}
```

**输出:**

```cs
Before Padding: 123
After Padding: 00123

```

**方法 3:使用** [**PadLeft**](https://www.geeksforgeeks.org/c-sharp-padleft-method/) **()方法****:****PadLeft****()**方法用于 通过填充字符串中的字符来向右对齐字符串中的字符。

> **第一步:**得到数字 N 和的前导零个数 p
> 
> **第二步:**使用 [ToString()方法将数字转换为字符串。](https://www.geeksforgeeks.org/c-sharp-int64-tostring-method-set-1/)
> 
> ```cs
> val = N.ToString();
> 
> ```
> 
> **第三步:**然后用 PadLeft() m 方法垫弦。
> 
> ```cs
> pad_str = val.PadLeft(P, '0');
> 
> ```
> 
> **第四步:**退回补好的绳子。

**示例:**

## C#

```cs
// C# program to pad an integer
// number with leading zeros
using System;

public class GFG{

    // Function to pad an integer number 
    // with leading zeros
    static string pad_an_int(int N, int P)
    {
        // use of ToString() method
        string value = N.ToString();

        // use of the PadLeft() method
        string pad_str = value.PadLeft(P, '0');

        // return output
        return pad_str;
    }

    // driver code
    public static void Main(string[] args)
    {
        int N = 123; // Number to be pad
        int P = 5; // Number of leading zeros

        Console.WriteLine("Before Padding: " + N);

        // Function calling
        Console.WriteLine("After Padding: " + pad_an_int(N, P));
    }
}
```

**输出:**

```cs
Before Padding: 123
After Padding: 00123

```