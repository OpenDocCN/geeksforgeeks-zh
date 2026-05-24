# C# | Copy()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-copy-method/](https://www.geeksforgeeks.org/c-sharp-copy-method/)

在 C# 中，Copy()是一个字符串方法。它用于为指定的字符串创建具有相同值的字符串的新实例。Copy()方法返回一个 String 对象，该对象与原始字符串相同，但表示不同的对象引用。若要检查其引用，请使用赋值操作，该操作将现有的字符串引用赋给附加的对象变量。

**语法:**

```cs
public static string Copy(string str)

```

**说明:**该方法接受单参数字符串，即需要复制的原始字符串。它返回字符串值，这是与字符串值相同的新字符串。复制()方法的类型是**系统。弦**。

**示例程序说明复制()方法**

```cs
// C# program to demonstrate the 
// use of Copy() method
using System;
class Program {

    static void cpymethod()
    {
        string str1 = "GeeksforGeeks";
        string str2 = "GFG";
        Console.WriteLine("Original Strings are str1 = "
            + "'{0}' and str2='{1}'", str1, str2);

        Console.WriteLine("");

        Console.WriteLine("After Copy method");
        Console.WriteLine("");

        // using the Copy method
        // to copy the value of str1 
        // into str2
        str2 = String.Copy(str1);

        Console.WriteLine("Strings are str1 = "
        +"'{0}' and str2='{1}'", str1, str2);

        // check the objects reference equal or not
        Console.WriteLine("ReferenceEquals: {0}",
            Object.ReferenceEquals(str1, str2));

        // check the objects are equal or not
        Console.WriteLine("Equals: {0}", Object.Equals(str1, str2));
        Console.WriteLine("");

        Console.WriteLine("After Assignment");
        Console.WriteLine("");

        // to str1 object reference assign to str2
        str2 = str1;

        Console.WriteLine("Strings are str1 = '{0}' "
                    +"and str2 = '{1}'", str1, str2);

        // check the objects reference equal or not
        Console.WriteLine("ReferenceEquals: {0}", 
            Object.ReferenceEquals(str1, str2));

        // check the objects are equal or not
        Console.WriteLine("Equals: {0}", Object.Equals(str1, str2));

    }

    // Main Method
    public static void Main()
    {

        // calling method
        cpymethod();
    }
}
```

**输出:**

```cs
Original Strings are str1 = 'GeeksforGeeks' and str2='GFG'

After Copy method

Strings are str1 = 'GeeksforGeeks' and str2='GeeksforGeeks'
ReferenceEquals: False
Equals: True

After Assignment

Strings are str1 = 'GeeksforGeeks' and str2 = 'GeeksforGeeks'
ReferenceEquals: True
Equals: True

```

**参考:**T2】https://msdn.microsoft.com/en-us/library/system.string.copy