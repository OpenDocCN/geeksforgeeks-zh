# C# | Substring()方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-substring-method/](https://www.geeksforgeeks.org/c-sharp-substring-method/)

在 C# 中，`Substring()` 是一个字符串方法。它用于从字符串的当前实例中检索子字符串。通过向该方法传递不同数量的参数，可以重载该方法，如下所示:

*   `String.Substring(Int32)` 方法
*   `String.Substring(Int32, Int32)` 方法

## `String.Substring(Int32)` 方法

此方法用于从字符串的当前实例中检索子字符串。参数 `startIndex` 将指定子字符串的开始位置，然后子字符串将继续到字符串的末尾。

**语法:**

```cs
public string Substring(int startIndex)
```

*   **参数:** 此方法接受一个参数 `startIndex`。此参数将指定必须检索的子字符串的起始位置。该参数的类型为 `System.Int32`。
*   **返回值:** 该方法将返回从 `startIndex` 开始，一直延续到字符串末尾的子字符串。返回值类型为 `System.String`。

**异常:** 如果 `startIndex` 小于零或大于当前实例的长度，则会出现 `ArgumentOutOfRangeException`。

**示例:**

```cs
Input : str  = "GeeksForGeeks"
        str.Substring(5);
Output: ForGeeks

Input : str  = "GeeksForGeeks"
        str.Substring(8);
Output: Geeks
```

下面的程序说明了上面讨论的方法:

```cs
// C# program to demonstrate the 
// String.Substring Method (startIndex)
using System;
class Geeks {

    // Main Method
    public static void Main()
    {
        // define string
        String str = "GeeksForGeeks";

        Console.WriteLine("String    : " + str);

        // retrieve the substring from index 5
        Console.WriteLine("Sub String1: " + str.Substring(5));

        // retrieve the substring from index 8
        Console.WriteLine("Sub String2: " + str.Substring(8));
    }
}
```

**Output:**

```cs
String    : GeeksForGeeks
Sub String1: ForGeeks
Sub String2: Geeks
```

## `String.Substring(Int32, Int32)` 方法

该方法用于提取从参数 `startIndex` 描述的指定位置开始并具有指定 `length` 的子串。如果 `startIndex` 等于字符串长度，而参数 `length` 为零，那么它将不返回任何子字符串。

**语法:**

```cs
public string Substring(int startIndex, int length)
```

*   **参数:** 该方法接受两个参数 `startIndex` 和 `length`。第一个参数将指定必须检索的子字符串的起始位置，第二个参数将指定子字符串的长度。两个参数的类型都是 `System.Int32`。
*   **返回值:** 该方法将返回从指定位置开始的子串，子串将具有指定的长度。返回值类型为 `System.String`。

**异常:** 这个方法可以在两种情况下出现 `ArgumentOutOfRangeException`:

1.  如果参数 `startIndex` 或 `length` 小于零。
2.  如果 `startIndex + length` 表示不在当前实例中的位置。

**示例:**

```cs
Input : str  = "GeeksForGeeks"
        str.Substring(0,8);
Output: GeeksFor

Input : str  = "GeeksForGeeks"
        str.Substring(5,3);
Output: For

Input : str  = "Geeks"
        str.Substring(4,0);
Output:
```

下面的程序说明了上面讨论的方法:

```cs
// C# program to demonstrate the 
// String.Substring Method 
// (int startIndex, int length)
using System;
class Geeks {

    // Main Method
    public static void Main()
    {
        // define string
        String str = "GeeksForGeeks";

        Console.WriteLine("String    : " + str);

        // retrieve the substring from index 0 to length 8
        Console.WriteLine("Sub String1: " + str.Substring(0, 8));

        // retrieve the substring from index 5 to length 3
        Console.WriteLine("Sub String2: " + str.Substring(5, 3));
    }
}
```

**Output:**

```cs
String    : GeeksForGeeks
Sub String1: GeeksFor
Sub String2: For
```

**参考文献:**

*   [https://msdn.microsoft.com/en-us/library/hxthx5h6(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/hxthx5h6(v=vs.110).aspx)
*   [https://msdn.microsoft.com/en-us/library/aka44szs(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/aka44szs(v=vs.110).aspx)