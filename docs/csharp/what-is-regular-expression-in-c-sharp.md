# 什么是 C# 中的正则表达式？

> 原文:[https://www . geesforgeks . org/什么是 c-sharp 中的正则表达式/](https://www.geeksforgeeks.org/what-is-regular-expression-in-c-sharp/)

在 C# 中，正则表达式是一种模式，用于解析和检查给定的输入文本是否与给定的模式匹配。在 C# 中，正则表达式通常被称为 C# 正则表达式。[。Net Framework](https://www.geeksforgeeks.org/introduction-to-net-framework/) 提供了一个允许模式匹配的正则表达式引擎。模式可以由任何字符文字、运算符或构造函数组成。
C# 提供了一个名为 Regex 的类，可以在[系统中找到。](https://docs.microsoft.com/en-us/dotnet/api/system.text.regularexpressions?view=netframework-4.8)命名空间。这门课将做两件事:

*   解析正则表达式模式的输入文本。
*   识别给定文本中的正则表达式模式。

**示例 1:** 以下示例演示了 regex 在手机号码验证中的使用。假设您正在制作一个表单，需要验证用户输入的手机号码，然后可以使用 regex。

## C#

```cs
// C# program to validate the Mobile
// Number using Regular Expressions
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Input strings to Match
        // valid mobile number
        string[] str = {"9925612824",
          "8238783138", "02812451830"};

        foreach(string s in str)
        {
            Console.WriteLine("{0} {1} a valid mobile number.", s,
                        isValidMobileNumber(s) ? "is" : "is not");
        }

        Console.ReadKey();
    }

    // method containing the regex
    public static bool isValidMobileNumber(string inputMobileNumber)
    {
        string strRegex = @"(^[0-9]{10}$)|(^\+[0-9]{2}\s+[0-9]
                {2}[0-9]{8}$)|(^[0-9]{3}-[0-9]{4}-[0-9]{4}$)";

        // Class Regex Represents an
        // immutable regular expression.
        //   Format                Pattern
        // xxxxxxxxxx           ^[0 - 9]{ 10}$
        // +xx xx xxxxxxxx     ^\+[0 - 9]{ 2}\s +[0 - 9]{ 2}\s +[0 - 9]{ 8}$
        // xxx - xxxx - xxxx   ^[0 - 9]{ 3} -[0 - 9]{ 4}-[0 - 9]{ 4}$
        Regex re = new Regex(strRegex);

        // The IsMatch method is used to validate
        // a string or to ensure that a string
        // conforms to a particular pattern.
        if (re.IsMatch(inputMobileNumber))
            return (true);
        else
            return (false);
    }
}
```

**输出:**

```cs
9925612824 is a valid mobile number.
8238783138 is a valid mobile number.
02812451830 is not a valid mobile number.
```

**示例 2:** 下面的示例演示了正则表达式在电子邮件标识验证中的使用。假设您正在制作一个表单，您需要验证用户输入的电子邮件 id，然后您可以使用 regex。

## C#

```cs
// C# program to validate the Email
// ID using Regular Expressions
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Input strings for Match
        // valid E-mail address.
        string[] str = {"parth@gmail.com",
                  "parthmaniyargmail.com",
                            "@gmail.com"};

        foreach(string s in str)
        {
            Console.WriteLine("{0} {1} a valid E-mail address.", s,
                                isValidEmail(s) ? "is" : "is not");
        }

    }

    // Method to check the Email ID
    public static bool isValidEmail(string inputEmail)
    {

        // This Pattern is use to verify the email
        string strRegex = @"\A(?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?)\Z";

        Regex re = new Regex(strRegex, RegexOptions.IgnoreCase);

        if (re.IsMatch(inputEmail))
            return (true);
        else
            return (false);
    }
}
```

**输出:**

```cs
parth@gmail.com is a valid E-mail address.
parthmaniyargmail.com is not a valid E-mail address.
@gmail.com is not a valid E-mail address.
```

### 正则表达式语法

有许多基本的语法，如量词、特殊字符、字符类、分组&替代用于正则表达式。

**量词:**

<figure class="table">

| 子表达式(贪婪) | 子表达式(惰性) | 比赛 |
| --- | --- | --- |
| * | *? | 用于零次或多次匹配前面的字符。 |
| + | +? | 用于一次或多次匹配前面的字符。 |
| ？ | ？？ | 用于匹配前面的字符零或一次。 |
| {n} | {n}？ | 用于与前面的字符精确匹配 n 次。 |
| {n，} | {n，}？ | 用于匹配前面的字符至少 n 次。 |
| {n，m} | {n，m}？ | 用于匹配前面的字符 n 到 m 次。 |

</figure>

**例 1:**

## C#

```cs
// C# program to demonstrate
// the * Quantifier
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    public static void Main(string[] args)
    {
        // This will return any
        // pattern b, ab, aab, ...
        Regex regex = new Regex(@"a*b");

        Match match = regex.Match("aaaabcd");
        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }
    }
}
```

**输出:**

```cs
Match Value: aaaab
```

**例 2:**

## C#

```cs
// C# program to demonstrate
// the + Quantifier
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    public static void Main()
    {

        // this will return any pattern
        // like ab, aab, aaab, ....
        Regex regex = new Regex(@"a+b");
        Match match = regex.Match("aaabcd");
        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }
    }
}
```

**输出:**

```cs
Match Value: aaab
```

**例 3:**

## C#

```cs
// C# program to demonstrate
// the ? Quantifier
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    static void Main()
    {

         // This return any pattern like b, ab
        Regex regex = new Regex(@"a?b");

        Match match = regex.Match("aaaabcd");

        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }
    }
}
```

**输出:**

```cs
Match Value: ab
```

**特殊字符**

<figure class="table">

| 子表达式 | 比赛 |
| --- | --- |
| ^ | 此元素后的单词与字符串或行的开头匹配。 |
| $ | 此元素之前的单词在行或字符串的末尾匹配。 |
| 。(点) | 只匹配任何字符一次，除了\n(新行)。 |
| \d | 它用于匹配数字字符。 |
| \D | 它用于匹配非数字字符。 |
| \w | 它用于匹配任何字母数字和下划线字符。 |
| \W | 它用于匹配任何非单词字符。 |
| \s | 它用于匹配空白字符。 |
| \S | 它用于匹配非空白字符。 |
| \n | 它用于匹配换行符。 |

</figure>

**例 1:**

## C#

```cs
// C# program to demonstrate
// the ^ Special Character
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    static void Main()
    {

        // This will return if shyam exist
        // at the beginning of the line
        Regex regex = new Regex(@"^Shyam");

        Match match = regex.Match("Shyam is my pet name");

        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }
    }
}
```

**输出:**

```cs
Match Value: Shyam
```

**例 2:**

## C#

```cs
// C# program to demonstrate
// the $ Special Character
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    public static void Main()
    {

        // This return parth if it
        // exist at the end of the line
        Regex regex = new Regex(@"Parth{content}quot;);

        Match match = regex.Match("My name is Parth");

        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }
    }
}
```

**输出:**

```cs
Match Value: Parth
```

**例 3:**

## C#

```cs
// C# program to demonstrate
// the .(Dot) Special Character
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    static void Main()
    {
         // This will return any word which
         // contains only one letter between
         // s and t
        Regex regex = new Regex(@"s..t");

        Match match = regex.Match("This is my seat");

        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }
    }
}
```

**输出:**

```cs
Match Value: seat
```

**例 4:**

## C#

```cs
// C# program to demonstrate
// the \d Special Character
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    static void Main()
    {
        // This will the return
        // the one digit character
        Regex regex = new Regex(@"\d");

        Match match = regex.Match("I am 19 years old");

        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }

    }
}
```

**输出:**

```cs
Match Value: 1
```

**字符类**

<figure class="table">

| 子表达式 | 比赛 |
| --- | --- |
| [] | 它用于匹配字符范围 |
| [a-z] | 它用于匹配 a-z 范围内的任何字符。 |
| [^a-z] | 它用于匹配不在 a-z 范围内的任何字符。 |
| \ | 它用于匹配转义特殊字符。 |

</figure>

**例 1:**

## C#

```cs
// C# program to demonstrate
// the [] character class
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    static void Main()
    {

        // This will return one character either
        // a or b or c which will come first
        Regex regex = new Regex(@"[abc]");

        Match match = regex.Match("abcdef");

        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }
    }
}
```

**输出:**

```cs
Match Value: a
```

**例 2:**

## C#

```cs
// C# program to demonstrate
// the [a-z] character class
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    static void Main()
    {

        // This will return any character
        // between x and z inclusive
        Regex regex = new Regex(@"[x-z]");

        Match match = regex.Match("xmax");

        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }
    }
}
```

**输出:**

```cs
Match Value: x
```

**例 3:**

## C#

```cs
// C# program to demonstrate
// the [^a-z] character class
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    static void Main()
    {

        // This will return other x,
        // y and z character
        Regex regex = new Regex(@"[^x-z]");

        Match match = regex.Match("xmax");

        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }
    }
}
```

**输出:**

```cs
Match Value: m
```

**分组和备选方案**

<figure class="table">

| 子表达式 | 比赛 |
| --- | --- |
| () | 它用于组表达式 |
| (a&# 124;b) | &# 124;运算符用于替代项 a 或 b。 |
| (?是&# 124;否) | 如果表达式匹配，则给出是，否则给出否。 |

</figure>

**例 1:**

## C#

```cs
// C# program to demonstrate
// the grouping in regex
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    static void Main()
    {

        // This will return pattern
        // will cd, cdcd, cdcdcd, ...
        Regex regex = new Regex(@"(cd)+");

        Match match = regex.Match("cdcdde");

        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }
    }
}
```

**输出:**

```cs
Match Value: cdcd
```

**例 2:**

## C#

```cs
// C# program to demonstrate
// the grouping in regex
using System;
using System.Text.RegularExpressions;

class GFG {

    // Main Method
    static void Main()
    {

        // This will either d or e
        // which ever comes first
        Regex regex = new Regex(@"d|e");

        Match match = regex.Match("edge");

        if (match.Success)
        {
            Console.WriteLine("Match Value: " + match.Value);
        }
    }
}
```

**输出:**

```cs
Match Value: e
```