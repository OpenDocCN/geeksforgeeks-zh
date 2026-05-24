# C# | PadLeft()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-padleft-method/](https://www.geeksforgeeks.org/c-sharp-padleft-method/)

在 C# 中 ***PadLeft()*** 是一个 **[串](https://www.geeksforgeeks.org/c-string/)** 的方法。此方法用于将字符串中的字符右对齐，方法是在指定的总长度内用空格或左边的指定字符填充它们。这个方法可以通过传递不同的参数来重载。

*   字符串。PadLeft 方法(Int32)
*   字符串。左对齐方法(Int32，Char)

#### 

字符串。PadLeft 方法(Int32)

此方法用于通过在左边填充空格来右对齐字符串中的字符。参数“totalWidth”将指定字符串中的填充字符数，此方法将返回一个新字符串。

**语法:**

```cs
public string PadLeft(int totalWidth)
```

*   **参数:**该方法将接受一个参数“ *totalWidth* ，该参数指定字符串中填充字符的数量。该参数的类型为**系统。Int32** 。
*   **返回值:**这个方法将返回填充字符串右边部分的字符串。返回值类型为**系统。弦**。
*   **异常:**如果总宽度小于零，则会出现***argumentout of range Exception***。

**示例:**程序演示**公共字符串 PadLeft(int totalWidth)** 方法。字符串是右对齐的，并根据需要在左边填充空白，以创建一个长度为 totalWidth 的字符串。但是，如果 totalWidth 小于或等于字符串的长度，该方法将返回一个与字符串相同的新字符串。例如，如果当前字符串是“极客”，总宽度是 7，那么 PadLeft 方法返回“极客”。

```cs
// C# program to illustrate the
// String.PadLeft(totalWidth) method
using System;
class Geeks {

    // Main Method
    public static void Main()
    {
        string s1 = "GeeksForGeeks";

        Console.WriteLine("String : " + s1);

        // totalwidth is less than string length
        Console.WriteLine("Pad  2 :'{0}'", s1.PadLeft(2));

        // totalwidth is equal to string length
        Console.WriteLine("Pad 13 :'{0}'", s1.PadLeft(13));

        // totalwidth is greater then string length
        Console.WriteLine("Pad 20 :'{0}'", s1.PadLeft(20));
    }
}
```

**输出:**

```cs
String : GeeksForGeeks
Pad  2 :'GeeksForGeeks'
Pad 13 :'GeeksForGeeks'
Pad 20 :'       GeeksForGeeks'

```

#### 

字符串。左对齐方法(Int32，Char)

此方法用于通过在左边填充*指定字符*来右对齐该字符串中的字符。参数“*总宽度*”将指定字符串中的填充字符数，而“*填充字符”*是指定的字符。

**语法:**

```cs
public string PadLeft(int totalWidth, char paddingChar)

```

*   **参数:**该方法接受两个参数“*总宽度*”和“*帕丁查尔*”。参数“总宽度”将指定字符串中填充字符的数量，该参数的类型为**系统。Int32** 。参数“填充字符”将指定填充字符，该参数的类型为**系统。Char** 。
*   **返回值:**此方法将返回一个新字符串，该字符串将等效于当前字符串，但会右对齐，并在左边填充“paddingChar”参数指定的字符。如果 totalWidth 小于字符串的长度，则该方法返回相同的字符串。如果 totalWidth 等于字符串的长度，则该方法返回一个与当前字符串相同的新字符串。返回值类型为**系统。弦**。
*   **异常:**如果总宽度小于零，则会出现**argumentout of range Exception**。

**示例:**程序演示**公共字符串 PadLeft(int totalWidth，char paddingChar)** 方法。该字符串是右对齐的，并根据需要在左侧填充任意数量的字符，以创建总宽度长度。但是，如果 totalWidth 小于或等于此实例的长度，则该方法将返回与此实例相同的新字符串。例如，如果当前字符串是“极客”，totalWidth 是 7，paddingChar 是“*”，那么 PadLeft 方法返回“* *极客”。

```cs
// C# program to illustrate the
// String.PadLeft(int totalWidth, 
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
        Console.WriteLine("Pad 2 :'{0}'", s1.PadLeft(2, pad));

        // totalwidth is equal to string length
        Console.WriteLine("Pad 13 :'{0}'", s1.PadLeft(13, pad));

        // totalwidth is greater then string length
        Console.WriteLine("Pad 20 :'{0}'", s1.PadLeft(20, pad));
    }
}
```

**输出:**

```cs
String : GeeksForGeeks
Pad 2 :'GeeksForGeeks'
Pad 13 :'GeeksForGeeks'
Pad 20 :'*******GeeksForGeeks'

```

**关于 PadLeft()方法的要点:**

*   如果 PadLeft 方法用空白字符填充当前实例，此方法不会修改当前实例的值。相反，它返回一个用前导空格填充的新字符串，这样它的总长度就是 totalWidth 字符。
*   如果 totalWidth 小于 String 的长度，则该方法返回对现有实例的引用。

**参考文献:**

*   [https://msdn . Microsoft . com/en-us/library/system . string . padleft 1](https://msdn.microsoft.com/en-us/library/0zk6ydzx(v=vs.110).aspx)
*   [https://msdn . Microsoft . com/en-us/library/system . string . padleft 2](https://msdn.microsoft.com/en-us/library/92h5dc07%28v=vs.110%29.aspx?f=255&MSPPError=-2147217396)