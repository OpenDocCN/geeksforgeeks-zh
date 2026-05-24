# C# | String vs StringBuilder

> 原文:[https://www . geesforgeks . org/c-sharp-string-vs-string builder/](https://www.geeksforgeeks.org/c-sharp-string-vs-stringbuilder/)

#### 先决条件:[c# 中的字符串](https://www.geeksforgeeks.org/c-string/)

StringBuilder 用于表示字符的*可变字符串*。可变是指可以改变的字符串。所以字符串对象是不可变的，但是字符串生成器是可变的字符串类型。它不会创建当前字符串对象的新修改实例，而是在现有字符串对象中进行修改。StringBuilder 的完整功能由出现在`System.Text`命名空间中的 StringBuilder 类提供。

**字符串构建器的需求:**如上所述，字符串类对象是不可变的，这意味着如果用户修改任何字符串对象，将导致创建一个新的字符串对象。这使得使用细绳成本很高。因此，当用户需要对字符串进行重复操作时，StringBuilder 的需求就出现了。它提供了处理重复和多字符串操作的优化方法。

**示例:**

```cs
// C# program to demonstrate the
// difference between String,
// StringBuilder
using System;
using System.Text;
using System.Collections;

class GFG {
    // Concatenates to String
    public static void concat1(String s1)
    {

        // taking a string which
        // is to be Concatenate
        String st = "forGeeks";

        // using String.Concat method
        // you can also replace it with
        // s1 = s1 + "forgeeks";
        s1 = String.Concat(s1, st);
    }

    // Concatenates to StringBuilder
    public static void concat2(StringBuilder s2)
    {

        // using Append method
        // of StringBuilder class
        s2.Append("forGeeks");
    }

    // Main Method
    public static void Main(String[] args)
    {

        String s1 = "Geeks";
        concat1(s1); // s1 is not changed
        Console.WriteLine("Using String Class: " + s1);

        StringBuilder s2 = new StringBuilder("Geeks");
        concat2(s2); // s2 is changed
        Console.WriteLine("Using StringBuilder Class: " + s2);
    }
}
```

**输出:**

```cs
Using String Class: Geeks
Using StringBuilder Class: GeeksforGeeks

```

**说明:**

*   **concat 1 方法的使用:**在这个方法中，我们传递一个字符串“ *Geeks* ”并执行“ *s1 = String。Concat(s1，ST)；*“其中 st 为”*锻造*”进行连接。从 Main()传递的字符串没有改变，这是因为字符串是不可变的。更改字符串的值会创建另一个对象，concat1()中的 *s1* 会存储新字符串的引用。但是 Main() 和 *concat1()* 中的 *s1 引用的是不同的字符串。*
*   **concat 2 方法的使用:**在这个方法中，我们传递一个字符串“Geeks”并执行“s2”。追加(“伪造”)，将字符串的实际值(在 Main 中)更改为“极客伪造”。这是因为 StringBuilder 是可变的，因此会改变它的值。

**什么时候用哪一个:**

*   如果字符串在整个程序中保持不变，那么使用字符串类对象，因为字符串对象是不可变的。
*   如果字符串可以改变(例如:字符串构造中的大量逻辑和操作)，那么使用 StringBuilder 是最好的选择。

**将字符串转换为 StringBuilder:**
要将字符串类对象转换为 StringBuilder 类对象，只需将字符串对象传递给 StringBuilder 类构造函数即可。

**示例:**

```cs
// C# program to demonstrate the
// conversion from String to StringBuilder.
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        String str = "Geeks";

        // conversion from String object
        // to StringBuilder
        StringBuilder sbl = new StringBuilder(str);
        sbl.Append("ForGeeks");
        Console.WriteLine(sbl);
    }
}
```

**输出:**

```cs
GeeksForGeeks
```

**将字符串构建器转换为字符串:**
可以使用 *ToString()* 方法执行该转换。

**示例:**

```cs
// C# program to demonstrate the
// conversion from String to StringBuilder
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        StringBuilder sbdr = new StringBuilder("Builder");

        // conversion from StringBuilder
        // object to String using ToString method
        String str1 = sbdr.ToString();

        Console.Write("StringBuilder object to String: ");
        Console.WriteLine(str1);
    }
}
```

**输出:**

```cs
StringBuilder object to String: Builder
```