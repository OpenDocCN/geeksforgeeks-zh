# C# |逐字字符串–@

> 原文:[https://www . geesforgeks . org/c-sharp-逐字-字符串-字面/](https://www.geeksforgeeks.org/c-sharp-verbatim-string-literal/)

在 C# 中，使用特殊符号 **@** 创建逐字字符串。@被称为逐字标识符。如果字符串包含@作为前缀，后跟双引号，则编译器会将该字符串识别为逐字字符串并编译该字符串。@ symbol 的主要优点是告诉字符串构造函数忽略转义字符和换行符。@符号主要有以下三种用法:

**使用 1:** ***关键字作为标识符***
该符号允许使用*关键字作为标识符*。@符号作为关键字的前缀，因此编译器将关键字作为标识符，没有任何错误，如下例所示:

**示例:**

```cs
// C# program to illustrate
// the use of @ by using keyword
// as an identifier
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating and initializing the array
        // here 'for' keyword is used as 
        // an identifier by using @ symbol
        string[] @for = {"C#", "PHP", "Java", "Python"};

                // as and for keywords is 
                // as an identifier
                // using @ symbol
                foreach (string @as in @for)
                {
                    Console.WriteLine("Element of Array: {0}", @as);
                }
    }
}
```

**Output:**

```cs
Element of Array: C#
Element of Array: PHP
Element of Array: Java
Element of Array: Python

```

**使用 2:** ***打印字符串中的转义序列，并使用换行符等。在没有任何转义序列的字符串中。***

如果将转义序列如*“\ \”*(用于反斜杠)、*“\ u”*(Unicode 转义序列)、*“\ x”*(十六进制转义序列)等。在不使用@符号的字符串中，编译器会自动解释这些序列。但是" "(双引号)不是字面意思。这就像一个字符串插值。让我们看看有和没有@符号的不同情况。

*   **Case 1:**

    ```cs
    // taking a string literal and 
    // try to print double quotes
    string str1 = """";

    // printing output
    // this will give compile
    // time error as Unexpected 
    // symbol `' 
    Console.WriteLine(str1);

    ```

    在上面的程序中，双引号内的双引号作为字符串文字被解释为单引号。

*   **Case 2:**

    ```cs
    // taking a string literal prefixes
    // with @ and try to print double quotes
    string str1 = @"""";

    // printing output
    // this will output as "
    Console.WriteLine(str1);

    ```

    在上面的程序中，输出是双引号(**“**)而不是**“**

*   **案例 3:**

    ```cs
    // taking a string in which we are storing 
    // some location of file but \Testing will 
    // interpreted as eascape sequence \T 
    // similarly \N
    string str1 = "\\C:\Testing\New\Target";

    // printing str1
    // this will give compile time error as
    // Unrecognized escape sequence `\T'
    // Unrecognized escape sequence `\N'
    // Unrecognized escape sequence `\T'
    Console.WriteLine(str1);

    ```

*   **案例 4:**

    ```cs
    // taking a string and prefix literal with @ symbol. 
    // Storing some location of file 
    string str1 = @"\\C:\Testing\New\Target";

    // printing str1 will give output as 
    // \\C:\Testing\New\Target
    Console.WriteLine(str1);

    ```

**程序:**

```cs
// C# program to illustrate
// the use of @ in terms of 
// escape sequences and new 
// line and tab
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // If you use the below commented
        // the part then this will give
        // Unrecognized escape sequence error
        // string S1 = "\\welcome \to GeeksforGeeks \ portal \";
        // Console.WriteLine("String 1 is :{0}", S1);

        // By using @ in the given string 
        // it runs smoothly because
        // @ symbol tells the compiler to
        // ignore all escape sequences
        string S2 = @"\\welcome \to GeeksforGeeks \ portal \";
        Console.WriteLine("String 2 is: {0}", S2);

        // printing new line character in string literal
        // but it will make the string to break  
        // into a new line, see output
        string S3 = "This is \n C# non verbatim string";
        Console.WriteLine("String 3 is :{0}", S3);

        // By using @ symbol /n does not processed
        string S4 = @"This is \n C# verbatim string";
        Console.WriteLine("String 4 is :{0}", S4);

        // printing a string literal contains 
        // tabs and new line without using 
        // any escape sequence
        Console.WriteLine(@"Without Tab Sequence and New Line Character
                               C          C++      Java       Python");
    }
}
```

**Output:**

```cs
String 2 is: \\welcome \to GeeksforGeeks \ portal \
String 3 is :This is 
 C# non verbatim string
String 4 is :This is \n C# verbatim string
Without Tab Sequence and New Line Character
                               C          C++      Java       Python

```