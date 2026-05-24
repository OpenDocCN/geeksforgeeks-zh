# C# |字符串属性

> 原文:[https://www.geeksforgeeks.org/c-sharp-string-properties/](https://www.geeksforgeeks.org/c-sharp-string-properties/)

该字符串是一个字符数组。字符串类将文本表示为一系列 Unicode 字符，并在 **[中定义。NET](https://www.geeksforgeeks.org/c-net-framework-basic-architecture-component-stack/)** 基础类库。String 类的主要用途是提供属性和方法，这样处理字符串就变得容易了。

字符串类有**两个属性**:

1.  **Chars[Int32]** :用于获取当前字符串对象中指定位置的 Char 对象。在 C# 中，Chars 属性是一个索引器。
2.  **长度**:用于获取当前 String 对象中的字符数。

#### 

字符串。字符属性(Int32)

**语法:**

```cs
public char this[int index] 
{ 
      get; 
}

```

*   **参数:**该方法只取一个参数，即当前字符串中的位置索引，类型为**系统。Int32** 。索引参数从零开始。
*   **返回值:**该方法在索引参数指定的位置返回 Char 对象，其属性值类型为**系统。充电**。

下面是说明字符属性的程序:

*   **程序 1:** 字符串中的每个 Char 对象都可以通过使用如下代码来访问。。

    ```cs
    // C# program to demonstrate the 
    // Chars property of String class
    using System;
    class Geeks {

    // Main Method
    public static void Main()
    {
        string str = "GeeksforGeeks";
        for (int i = 0; i <= str.Length - 1; i++ )
        Console.Write("{0} ", str[i]);
    }
    }
    ```

    **输出:**

    ```cs
    G e e k s f o r G e e k s

    ```

*   **程序 2:** 在例程中使用该索引器来验证字符串。

    ```cs
    // C# program to check the whether the 
    // character is number or character
    using System;
    class Geeks {

        // Main Method
        public static void Main()
        {
            string str = "11Gee45for78geeks";

            for (int i = 0; i < str.Length; i++)
            {
                if (Char.IsDigit(str[i]))
                    Console.WriteLine("{0} is a Number.", str[i]);
                else
                    Console.WriteLine("{0} is a character.", str[i]);
            }
        }
    }
    ```

    **输出:**

    ```cs
    1 is a Number.
    1 is a Number.
    G is a character.
    e is a character.
    e is a character.
    4 is a Number.
    5 is a Number.
    f is a character.
    o is a character.
    r is a character.
    7 is a Number.
    8 is a Number.
    g is a character.
    e is a character.
    e is a character.
    k is a character.
    s is a character.

    ```

#### 

字符串。长度属性

Length 属性返回此实例中字符对象的数量，而不是 Unicode 字符的数量，因为一个 Unicode 字符可能由多个字符表示。

**语法:**

```cs
public int Length 
{ 
    get;
}

```

*   **返回值:**返回字符串实例中字符对象的数量。

**注意:**在 C 和 C++中，空字符表示字符串的结尾，但在 C# 中，空字符可以嵌入到字符串中。当一个字符串包含一个或多个空字符时，它也会考虑该字符串的总长度。例如，如果在字符串中，子字符串“xyz”和“abc”由空字符分隔，如字符串值为“xyz\0abc”，则 Length 属性返回 7，其中包括六个字母字符和空字符。

以下是说明长度属性的程序:

*   **程序 1:**

    ```cs
    // C# program to demonstrate the 
    // Length property
    using System;
    class Geeks
    {

       // Main Method
       public static void Main()
       {

          // here include four null character
          // between xyz and abc substring
          string str = "xyz\0\0\0\0abc";
          Console.WriteLine(str.Length); 
       }
    }
    ```

    **输出:**

    ```cs
    10

    ```

*   **程序二:**

    ```cs
    // C# program to illustrate the 
    // Length property of String class
    using System;
    class Geeks {

    // Main Method
    public static void Main()
    {

            // taking the string variable
            // and then find length
        string str = "GeeksforGeeks";

        Console.WriteLine("'{0}' length : {1}", str, str.Length);

             // Directly use length property 
            // with string here no variable use 
        Console.WriteLine("'{0}' length : {1}", "GEEKS", "GEEKS".Length);

            // return value stored the in 
            // integer variable l
        int l = str.Length;
        Console.WriteLine("'{0}' length : {1}", str, l);
    }
    }
    ```

    **输出:**

    ```cs
    'GeeksforGeeks' length : 13
    'GEEKS' length : 5
    'GeeksforGeeks' length : 13

    ```

**参考文献:**

*   [https://msdn . Microsoft . com/en-us/library/system . string . chars](https://msdn.microsoft.com/en-us/library/system.string.chars(v=vs.110).aspx?cs-save-lang=1&cs-lang=csharp# code-snippet-1)
*   [https://msdn . Microsoft . com/en-us/library/system . string . length](https://msdn.microsoft.com/en-us/library/system.string.length(v=vs.110).aspx?cs-save-lang=1&cs-lang=csharp# code-snippet-2)