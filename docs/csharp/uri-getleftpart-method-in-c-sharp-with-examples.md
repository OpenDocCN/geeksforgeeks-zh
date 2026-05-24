# 乌利。C# 中的 GetLeftPart()方法，带示例

> 原文:[https://www . geesforgeks . org/uri-getleftpart-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uri-getleftpart-method-in-c-sharp-with-examples/)

**乌利。GetLeftPart()方法**是一个实例方法，用于根据传递的 UriPartial 枚举从给定的 URI 获取指定的部分。

> ***语法:*** 字符串 Uri。getleft Part(uri Part)；
> 
> ***参数:***
> 
> *   **零件** *:代表 UriPartial 从 Uri 获取指定零件。*
> 
> ***返回值:**此方法*返回字符串值来表示 Uri 的指定部分。
> 
> **异常:**有两种类型的异常是:
> 
> *   **系统。参数异常:**如果指定的部分无效。
> *   **系统。如果当前 Uri 实例不是绝对实例，则无效操作异常:**。

下面的程序说明了 **Uri 的使用。GetLeftPart()** 方法:

**例 1:**

## C#

```cs
// C# program to demonstrate the 
// Uri.GetLeftPart() Method 
using System; 
using System.Globalization; 

class GFG { 

     // Main Method 
    public static void Main() 
    { 
        // Declaring and initializing Uri 
        Uri  val;

        val = new Uri("https://www.geeksforgeeks.org/data-structure");

        // Use of Uri.GetLeftPart() Method
        // Getting the Authority
        string str = val.GetLeftPart(UriPartial.Authority);

        Console.WriteLine(str); 
    } 
}
```

**输出:**

```cs
https://www.geeksforgeeks.org

```

**例 2:**

## C#

```cs
// C# program to demonstrate the 
// Uri.GetLeftPart() Method 
using System; 
using System.Globalization; 

class GFG { 

     // Main Method 
    public static void Main() 
    { 
        // Declaring and initializing Uri 
        Uri  val;

        val = new Uri("https://www.geeksforgeeks.org/");

        // Use of Uri.GetLeftPart() Method
        // Getting the Path
        string str1 = val.GetLeftPart(UriPartial.Path);
        Console.WriteLine(str1); 

        // Getting the Query
        string str2 = val.GetLeftPart(UriPartial.Query);
        Console.WriteLine(str2);

        // Getting the Scheme
        string str3 = val.GetLeftPart(UriPartial.Scheme);
        Console.WriteLine(str3);
    } 
}
```

**输出:**

```cs
https://www.geeksforgeeks.org/
https://www.geeksforgeeks.org/
https://

```