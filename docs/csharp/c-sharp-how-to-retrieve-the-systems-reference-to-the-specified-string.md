# C# |如何检索系统对指定字符串的引用

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何检索系统-引用指定的字符串/](https://www.geeksforgeeks.org/c-sharp-how-to-retrieve-the-systems-reference-to-the-specified-string/)

**弦。实习生(字符串)方法**用于检索系统对指定[字符串](https://www.geeksforgeeks.org/c-string-class/)的引用。此方法使用实习生池搜索等于指定字符串值的字符串。
如果存在这样的字符串，则返回它在实习池中的引用，或者如果该字符串不存在，则将指定字符串的引用添加到实习池中，然后返回该引用。
这里的实习池是一个表，包含对程序中以编程方式声明或创建的每个唯一文字字符串的单个引用。
**语法:**

```cs
public static string Intern (string strA);
```

这里 *strA* 是在实习生池中搜索的字符串。
**返回值:**该方法的返回类型为**系统。弦**。如果系统被拘留，该方法将返回系统对 *strA* 的引用。否则，对值为 *strA* 的字符串的新引用。
**异常:**如果*字符串*为空，该方法将给出 ArgumentNullException。
下面给出一些例子，以便更好地理解实现:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate Intern() method
using System;  

public class GFG   
{   

    // main method
    public static void Main(string[] args)   
    {   

        // string
       string strA = "This is C# tutorial"; 

       // retrieve the system reference
       // of strA string by
       // using Intern() method
       string strB = string.Intern(strA); 

       // Display the strings
       Console.WriteLine(strA); 
       Console.WriteLine(strB); 
    }   
}   
```

**Output:** 

```cs
This is C# tutorial
This is C# tutorial
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// use of Intern() Method
using System;

class GFG {

    public static void Main()
    {

        // strings
        string strA = "GeeksforGeeks";
        string strB = "GFG";
        string strC = "Noida";
        string strD = String.Intern(strA);
        string strE = String.Intern(strC);

        // Display string
        Console.WriteLine("string A == '{0}'", strA);
        Console.WriteLine("string B == '{0}'", strB);
        Console.WriteLine("string C == '{0}'", strC);
        Console.WriteLine("string D == '{0}'", strD);
        Console.WriteLine("string E == '{0}'", strE);
        Console.WriteLine();

        // Check the reference of strings
        Console.WriteLine("Is string A have the same reference as string B: {0}",
                                                    (Object)strA == (Object)strB);

        Console.WriteLine("Is string B have the same reference as string C: {0}",
                                                    (Object)strB == (Object)strC);

        Console.WriteLine("Is string D have the same reference as string E: {0}",
                                                    (Object)strD == (Object)strE);

        Console.WriteLine("Is string A have the same reference as string D: {0}",
                                                    (Object)strA == (Object)strD);

        Console.WriteLine("Is string E have the same reference as string C: {0}",
                                                    (Object)strE == (Object)strC);
    }
}
```

**Output:** 

```cs
string A == 'GeeksforGeeks'
string B == 'GFG'
string C == 'Noida'
string D == 'GeeksforGeeks'
string E == 'Noida'

Is string A have the same reference as string B: False
Is string B have the same reference as string C: False
Is string D have the same reference as string E: False
Is string A have the same reference as string D: True
Is string E have the same reference as string C: True
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . string . intern？视图= net framework-4 . 7 . 2 # 定义](https://docs.microsoft.com/en-us/dotnet/api/system.string.intern?view=netframework-4.7.2# definition)