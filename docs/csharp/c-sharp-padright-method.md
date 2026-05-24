# C# | PadRight()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-padright-method/](https://www.geeksforgeeks.org/c-sharp-padright-method/)

在 C# 中 ***PadRight()*** 是一个字符串方法。此方法用于将字符串中的字符左对齐，方法是在指定的总长度内用空格或右侧的指定字符填充它们。这个方法可以通过传递不同的参数来重载。

*   字符串。帕德赖特方法(Int32)
*   字符串。帕德赖特方法(Int32，Char)

#### 

字符串。帕德赖特方法(Int32)

此方法用于通过在右侧用*空格*填充字符串来左对齐字符串中的字符。参数“*总宽度*”将指定字符串中填充字符的数量，该方法将返回一个新字符串。

**语法:**

```cs
public string PadRight(int totalWidth)

```

*   **参数:**该方法将接受一个参数“ *totalWidth* ，该参数指定字符串中填充字符的数量。该参数的类型为**系统。Int32** 。
*   **返回值:**这个方法将返回填充字符串左边部分的字符串。返回值类型为**系统。弦**。

**异常:**如果总宽度小于零，则会出现***argumentout of range Exception***。

**示例:**

```cs
Input : str  = "GeeksForGeeks"
        str.PadRight(2);
Output: 'GeeksForGeeks' 

// String is same because totalWidth 
// is less than length of String.

Input : str  = "GeeksForGeeks"
        str.PadRight(13);
Output: 'GeeksForGeeks' 

// String is same because of totalWidth 
// is equal to the length of String.

Input : str  = "GeeksForGeeks"
        str.PadRight(20);
Output: 'GeeksForGeeks       '   

// String is changed because of totalWidth
// is greater than the length of String.

So Right Padding will show only if the 
totalWidth is greater than string length.

```

下面的程序说明了上面讨论的方法:

```cs
// C# program to illustrate the
// String.PadRight(totalWidth) method
using System;
class Geeks {

    // Main Method
    public static void Main()
    {
        string s1 = "GeeksForGeeks";

        Console.WriteLine("String : " + s1);

        // totalwidth is less than string length
        Console.WriteLine("Pad 2 :'{0}'", s1.PadRight(2));

        // totalwidth is equal to string length
        Console.WriteLine("Pad 13 :'{0}'", s1.PadRight(13));

        // totalwidth is greater then string length
        Console.WriteLine("Pad 20 :'{0}'", s1.PadRight(20));
    }
}
```

**Output:**

```cs
String : GeeksForGeeks
Pad 2 :'GeeksForGeeks'
Pad 13 :'GeeksForGeeks'
Pad 20 :'GeeksForGeeks       '

```

#### 

字符串。帕德赖特方法(Int32，Char)

此方法用于通过用右侧的*指定字符*填充来左对齐该字符串中的字符。参数“*总宽度*”将指定字符串中的填充字符数，而“*填充字符”*是指定的字符。

**语法:**

```cs
public string PadRight(int totalWidth, char paddingChar)

```

*   **参数:**该方法接受两个参数“*总宽度*”和“*帕丁查尔*”。参数“总宽度”将指定字符串中填充字符的数量，该参数的类型为**系统。Int32** 。参数“填充字符”将指定填充字符，该参数的类型为**系统。Char** 。
*   **返回值:**此方法将返回一个新字符串，该字符串将等效于当前字符串，但会左对齐，并在右侧填充“paddingChar”参数指定的字符。如果 totalWidth 小于字符串的长度，则该方法返回相同的字符串。如果 totalWidth 等于字符串的长度，则该方法返回一个与当前字符串相同的新字符串。返回值类型为**系统。弦**。

**异常:**如果总宽度小于零，则会出现**argumentout of range Exception**。

**示例:**

```cs
Input : str  = "GeeksForGeeks"
        str.PadRight(2, '*');
Output: 'GeeksForGeeks' 

// String is same because totalWidth
// is less than the length of String.

Input : str  = "GeeksForGeeks"
        str.PadRight(13, '*');
Output: 'GeeksForGeeks' 

// String is same because of totalWidth
// is equal to the length of String.

Input : str  = "GeeksForGeeks"
        str.PadRight(20, '*');
Output: 'GeeksForGeeks*******'   

// String is changed because totalWidth 
// is greater than the length of String.

```

下面的程序说明了上面讨论的方法:

```cs
// C# program to illustrate the
// String.PadRight(int totalWidth, 
// char paddingChar) method 
using System;
class Geeks {

    // Main Method
    public static void Main()
    {
        string s1 = "GeeksForGeeks";
        char pad = '*';
        Console.WriteLine("String : " + s1);

        // totalwidth is less than string length
        Console.WriteLine("Pad 2 :'{0}'", s1.PadRight(2, pad));

        // totalwidth is equal to string length
        Console.WriteLine("Pad 13 :'{0}'", s1.PadRight(13, pad));

        // totalwidth is greater then string length
        Console.WriteLine("Pad 20 :'{0}'", s1.PadRight(20, pad));
    }
}
```

**Output:**

```cs
String : GeeksForGeeks
Pad 2 :'GeeksForGeeks'
Pad 13 :'GeeksForGeeks'
Pad 20 :'GeeksForGeeks*******'

```

**参考文献:**

*   [https://msdn . Microsoft . com/en-us/library/system . string . padright 1](https://msdn.microsoft.com/en-us/library/34d75d7s(v=vs.110).aspx)
*   [https://msdn . Microsoft . com/en-us/library/system . string . padright 2](https://msdn.microsoft.com/en-us/library/36f2hz3a(v=vs.110).aspx)