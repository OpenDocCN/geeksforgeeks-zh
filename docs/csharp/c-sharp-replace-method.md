# C# | Replace()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-replace-method/](https://www.geeksforgeeks.org/c-sharp-replace-method/)

在 C# 中， ***替换()*** 的方法是一个字符串方法。此方法用于替换当前字符串对象中所有指定的 Unicode 字符或指定的字符串，并返回新的修改后的字符串。这个方法可以通过传递参数来重载。

**语法:**

```cs
public string Replace(char Oldchar, char Newchar)
or
public string Replace(string Oldvalue, string Newvalue)

```

**解释:**
第一种方法取两个参数 OldChar 和 Newchar，其中 Oldchar 是要替换的 Unicode 字符，Newchar 是替换所有出现的 Oldchar 的字符。
第二种方法还采用两个参数 Oldvalue 和 Newvalue，其中 Oldvalue 是要替换的字符串，Newvalue 是替换 Oldvalue 所有出现的字符串。这两种方法的返回类型值都是**系统。弦**。

**异常:**

*   **ArgumentNullException** :如果 OldValue 或 Oldchar 都为空。
*   **参数异常**如果 OldValue 或 Oldchar 是空字符串(" ")。

以下是演示上述方法的程序:

*   **示例 1:** 程序演示**公共字符串替换(char Oldchar，char Newchar)** 方法。指定字符的所有出现都被另一个指定字符替换。如果在当前字符串对象中找不到旧字符，则字符串保持不变。

    ```cs
    Input : str  = "GeeksForGeeks"
            str.Replace('s', 'G');
    Output: GeekGForGeekG

    Input : str  = "GeeksForGeeks"
            str.Replace('e', ' ');
    Output: G  ksForG  ks

    ```

    ```cs
    // C# program to illustrate the Replace()
    // Method with character parameter
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // string
            String str = "Geeks For Geeks";

            Console.WriteLine("OldString : " + str);

            // replace the character 's' with 'G'
            Console.WriteLine("NewString: " + str.Replace('s', 'G'));

            // oldString will remain unchanged
            // its return the modified string
            Console.WriteLine("\nOldString: " + str);

            // replace the character 'e' with space ' '
            Console.WriteLine("NewString: " + str.Replace('e', ' '));
        }
    }
    ```

    **输出:**

    ```cs
    OldString : Geeks For Geeks
    NewString: GeekG For GeekG

    OldString: Geeks For Geeks
    NewString: G  ks For G  ks

    ```

*   **示例 2:** 程序演示**公共字符串替换(字符串 Oldvalue，字符串 Newvalue)** 方法。当前字符串实例中指定字符串的所有匹配项都被另一个指定字符串替换。如果在当前字符串中找不到旧值，则字符串保持不变。

    ```cs
    Input:  str  = "Geeks For Geeks"
            str.Replace("Geeks", "---");
    Output: --- For ---

    Input:  str  = "Geeks For Geeks"
            str.Replace("For", "GFG");
    Output: Geeks GFG Geeks

    ```

    ```cs
    // C# program to illustrate the Replace
    // Method with string parameter
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // define string
            String str = "Geeks For Geeks";

            Console.WriteLine("OldString : " + str);

            // replace the string 'Geeks' with '---'
            // in string 'Geeks comes two time so replace two times
            Console.WriteLine("NewString: " + str.Replace("Geeks", "---"));

            // oldString will remain unchanged
            // its return the modified string
            Console.WriteLine("\nOldString: " + str);

            // replace the string 'For' with 'GFG'
            Console.WriteLine("NewString: " + str.Replace("For", "GFG"));
        }
    }
    ```

    **输出:**

    ```cs
    OldString : Geeks For Geeks
    NewString: --- For ---

    OldString: Geeks For Geeks
    NewString: Geeks GFG Geeks

    ```

**对字符串(替换链)执行多次替换操作:**

上面的 Replace()方法返回修改后的字符串，所以现在我们可以将对 Replace 方法的连续调用链接在一起，对字符串执行多次替换。方法调用从左到右执行。
在下面的例子中，对于给定的字符串“XXXXX”，首先用 Y 替换 X，然后用 Z 替换 Y，最后用 a 替换 Z。

**示例:**

```cs
// C# program to demonstrate the 
// multiple replacements calls
using System;

public class Geeks{

    // Main Method
    public static void Main()
    {
        String str = "XXXXX";
        Console.WriteLine("Old String: " + str);

        // chain together
        str = str.Replace('X', 'Y').Replace('Y', 'Z').Replace('Z', 'A');
        Console.WriteLine("New string: " + str);
    }
}
```

**Output:**

```cs
Old String: XXXXX
New string: AAAAA

```

**需要记住的要点:**

*   Replace()方法不修改当前实例的值。相反，它返回一个新字符串，其中旧值的所有出现都被新值替换，类似地，旧字符也被新字符替换。
*   它执行区分大小写的搜索来查找旧值或旧字符。如果新值为空，旧值的所有出现都将被删除。

**参考文献:**

*   [https://msdn . Microsoft . com/en-us/library/czx8s 9ts(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/czx8s9ts(v=vs.110).aspx)
*   [https://msdn . Microsoft . com/en-us/library/fk 49 WTC 1(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/fk49wtc1(v=vs.110).aspx)