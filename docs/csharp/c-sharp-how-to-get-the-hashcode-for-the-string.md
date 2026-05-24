# C# |如何获取字符串的 HashCode】

> 原文:[https://www . geesforgeks . org/c-sharp-how-get-hashcode-for-string/](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-hashcode-for-the-string/)

**GetHashCode()方法**用于获取指定字符串的哈希码。当您将此方法应用于字符串时，此方法将返回给定字符串的 32 位有符号整数哈希代码。

**语法:**

```cs
public override int GetHashCode ();
```

**返回值:**该方法的返回类型为**系统。Int32** 。此方法返回一个 32 位有符号整数哈希代码。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# program to illustrate 
// the GetHashCode() method
using System;

public class GFG {

    // main method
    static public void Main()
    {
        int s1, s2, s3;

        // strings
        string a1 = "abc";
        string a2 = "geeks";
        string a3 = "gfg";

        // Get hash code of the given string by
        // using GetHashCode() method
        s1 = a1.GetHashCode();
        s2 = a2.GetHashCode();
        s3 = a3.GetHashCode();

        // display strings and their hash code
        Console.WriteLine("Display strings");
        Console.WriteLine("string 1: {0} and hashcode: {1}", a1, s1);
        Console.WriteLine("string 2: {0} and hashcode: {1}", a2, s2);
        Console.WriteLine("string 3: {0} and hashcode: {1}", a3, s3);
    }
}
```

**Output:**

```cs
Display strings
string 1: abc and hashcode: 1099313834
string 2: geeks and hashcode: -1893508949
string 3: gfg and hashcode: -870054572

```

**例 2:**

```cs
// C# program to illustrate
// the GetHashCode() method
using System;

class GFG {

    // main method
    static public void Main()
    {

        // calling Hashcode method
        Hashcode("Hello");
        Hashcode("GFG");
        Hashcode("Geeks");
        Hashcode("Geeksforgeeks");
        Hashcode("C#");
        Hashcode("Tutorial");
    }

    // Hashcode method
    public static void Hashcode(String value)
    {
        int result;

        // get hash code of the entered strings
        result = value.GetHashCode();
        Console.WriteLine("String : {0} and HashCode: {1}", value, result);
    }
}
```

**Output:**

```cs
String : Hello and HashCode: -327378614
String : GFG and HashCode: 1999992308
String : Geeks and HashCode: -1893476149
String : Geeksforgeeks and HashCode: -2133923457
String : C# and HashCode: -1917577788
String : Tutorial and HashCode: 1463624248

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . string . gethashcode？视图= net framework-4 . 7 . 2 # 定义](https://docs.microsoft.com/en-us/dotnet/api/system.string.gethashcode?view=netframework-4.7.2# definition)