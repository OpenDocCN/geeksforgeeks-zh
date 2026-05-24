# C# |如何检索指定字符串的引用

> 原文：[https://www.geeksforgeeks.org/c-sharp-how-to-retrieve-a-reference-to-a-specified-string/](https://www.geeksforgeeks.org/c-sharp-how-to-retrieve-a-reference-to-a-specified-string/)

`String.IsInterned` 方法用于检索对指定字符串的引用。这个方法在实习池中查找指定的字符串。
如果指定的字符串已经被拘留，则返回对该实例的引用。否则，返回 `null`。这里的实习池是一个表，包含程序中声明的每个唯一文字字符串常量的单个实例，以及通过调用[实习方法](https://www.geeksforgeeks.org/c-how-to-retrieve-the-systems-reference-to-the-specified-string/)以编程方式添加的字符串的任何唯一实例。

**注：** 主要区别 `String.Intern(String)` 方法和 `String.IsInterned(String)` 方法是：如果字符串不存在，`Intern` 方法通过向 Intern 池添加指定字符串的引用来返回引用。但是，如果字符串不存在，则 `IsInterned` 方法返回 `null`。

**语法：**

```cs
public static string IsInterned (string strA);
```

在这里，`strA` 是一个字符串，用于在实习生池中搜索。

**返回值：** 该方法的返回类型为 `System.String`。如果引用存在于 CLR（公共语言运行时）实习生池中，该方法将返回对 `strA` 的引用。否则，返回 `null`。

**异常：** 这个方法会给出 `strA` 为 `null` 时的 `ArgumentNullException`。

下面给出了一些例子，以便更好地理解实现：

### 例 1：C#

```cs
// C# program to check if the given
// string is in intern pool or not
using System;

class GFG {

// main method
    public static void Main()
    {
        // strings
        string str1 = "Monday";
        string str2 = str1 + "-day";
        string[] pool = {"Tuesday", "Wednesday",
                         "Thursday", str2};

        // checking in intern pool
        foreach(var item in pool)
        {
            // retrieve reference of strings
            bool value = String.IsInterned(item) != null;

            if (value)
                // if the string in intern pool then print
                Console.WriteLine("{0}: Yes", item);
            else
                // if string in not intern pool then print
                Console.WriteLine("{0}: No", item);
        }
    }
}
```

**输出：**

```cs
Tuesday: Yes
Wednesday: Yes
Thursday: Yes
Monday-day: No
```

### 例 2：C#

```cs
// C# program to check if the given
// string is in intern pool or not
using System;

class GFG {

// main method
    public static void Main()
    {
        // strings
        string str1 = "Geeks";
        string str2 = str1 + "-day";

        // this will give error as
        // null is present in pool
        string[] pool = {"GFG", "DSA",
                         "C#", null};

        // checking in intern pool
        foreach(var item in pool)
        {
            // retrieve reference of strings
            bool value = String.IsInterned(item) != null;

            if (value)
                // if the string in intern pool then print
                Console.WriteLine("{0}: Yes", item);
            else
                // if string in not intern pool then print
                Console.WriteLine("{0}: No", item);
        }
    }
}
```

**运行时错误：**

> 未处理异常：
> System.ArgumentNullException：值不能为空。
> 参数名称：str

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.string.isinterned?view=netframework-4.7.2#System_String_IsInterned_System_String_](https://docs.microsoft.com/en-us/dotnet/api/system.string.isinterned?view=netframework-4.7.2#System_String_IsInterned_System_String_)