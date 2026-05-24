# C# |字符串

> 原文:[https://www.geeksforgeeks.org/c-sharp-string/](https://www.geeksforgeeks.org/c-sharp-string/)

在 C# 中， ***字符串*** 是一个 Unicode 字符序列或字符数组。Unicode 字符的范围是从 U+0000 到 U+FFFF。字符数组也被称为*文本*。所以字符串是文本的表示。字符串是一个重要的概念，人们会混淆字符串是关键字还是对象或类。所以让我们理清这个概念。
一个字符串用类 ***System 表示。弦*** 。*“字符串”关键字*是系统的别名。字符串类，而不是编写系统。字符串一可以使用*字符串*，这是 ***系统的简写。弦*** 类。所以我们可以说字符串和 string 都可以作为 System 的别名。字符串类。所以弦是系统的*对象*。字符串类。
**例:**

> string s1 = " GeeksforGeeks//使用字符串关键字
> 字符串 S2 =“GFG”创建字符串；//使用字符串类
> 系统创建字符串。String s3 = " Pro Geek//使用字符串类
> 创建字符串

字符串类在 [**中定义。NET**](https://www.geeksforgeeks.org/c-net-framework-basic-architecture-component-stack/) 基础类库。换句话说，字符串对象是*系统的连续集合。代表字符串的对象。内存中字符串对象的最大大小为 2GB，即大约 10 亿个字符。**系统。字符串类是不可变的**，即一旦创建，其状态就不能改变。
**程序:**说明如何**声明**字符串，**初始化**字符串。另外，下面的程序显示了一行字符串的声明和初始化。* 

## C#

```cs
// C# program to declare string using
// string, String and System.String
// and initialization of string
using System;
class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // declare a string Name using
        // "System.String" class
        System.String Name;

        // initialization of String
        Name = "Geek";

        // declare a string id using
        // using an alias(shorthand)
        // "String" of System.String
        // class
        String id;

        // initialization of String
        id = "33";

        // declare a string mrk using
        // string keyword
        string mrk;

        // initialization of String
        mrk = "97";

        // Declaration and initialization of
        // the string in a single line
        string rank = "1";

        // Displaying Result
        Console.WriteLine("Name: {0}", Name);
        Console.WriteLine("Id: {0}", id);
        Console.WriteLine("Marks: {0}", mrk);
        Console.WriteLine("Rank: {0}", rank);
    }
}
```

**Output:** 

```cs
Name: Geek
Id: 33
Marks: 97
Rank: 1
```

**字符串特征:**

*   它是一个引用类型。
*   它是不可变的(它的状态不能改变)。
*   它可以包含空值。
*   它覆盖了操作符 _==)。

**区别** ***串*** **和** ***系统。字符串*** **:**
字符串是 System.String 的别名，字符串和 System 都有。String 的意思是相同的，它不会影响应用程序的性能。“string”是 C# 中的关键字。所以主要的区别来自于上下文，如何使用这些:

*   字符串用于声明，而不是系统。字符串用于访问静态字符串方法。
*   字符串用于声明字段、属性等。它将使用预定义的类型 System.String。这是最简单的使用方法。
*   字符串必须使用系统。字符串类方法，如字符串。子字符串，字符串。IndexOf 等。该字符串只是 System.String 的别名

**注:** In。NET 中，文本被存储为 Char 对象的顺序集合，因此在 C# 字符串的末尾没有空终止字符。因此，C# 字符串可以包含任意数量的嵌入空字符(“0”)。
**字符串数组:**我们还可以创建字符串数组并为其赋值。字符串数组可以如下创建:

*   **语法:**

```cs
String [] array_variable  =  new  String[Length_of_array]
```

*   **示例:**说明字符串数组的创建和赋值

## C#

```cs
// C# program for an array of strings
using System;
class Geeks {

// Main Method
static void Main(string[] args)
{

    String[] str_arr = new String[3];

    // Initialising the array of strings
    str_arr[0] = "Geeks";
    str_arr[1] = "For";
    str_arr[2] = "Geeks";

    // printing String array
    for(int i = 0; i < 3; i++)
    {
        Console.WriteLine("value at Index position "+i+" is "+str_arr[i]);
    }

}
}
```

**Output:** 

```cs
value at Index position 0 is Geeks
value at Index position 1 is For
value at Index position 2 is Geeks
```

**从用户输入中读取字符串:**可以从用户输入中读取字符串。console 类的 ReadLine()方法用于从用户输入中读取字符串。

*   **示例:**

## C#

```cs
// C# program to demonstrate Reading
// String from User-Input
using System;
class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        Console.WriteLine("Enter the String");

        // Declaring a string object read_user
        // and taking the user input using
        // ReadLine() method
        String read_user = Console.ReadLine();

        // Displaying the user input
        Console.WriteLine("User Entered: " + read_user);

    }

}
```

**输入:**

> 你好极客们！

**输出:**

```cs
Enter the String
User Entered: Hello Geeks !
```

**创建字符串的不同方式:**

*   从文字创建字符串
*   使用串联创建字符串
*   使用构造函数创建字符串
*   使用属性或方法创建字符串
*   使用格式创建字符串

**从文字创建字符串:**这是创建字符串最常见的方式。在这种情况下，用户必须定义字符串变量，然后在双引号内赋值。我们可以在双引号内使用任何类型的字符，除了像反斜杠(\)这样的特殊字符。

*   **程序:**说明使用文字创建字符串

## C#

```cs
// C# program to demonstrate the
// string creation using literals
using System;
class Geeks {

    // Main Method
    static void Main(string[] args)
    {
        string str1 = "GeeksforGeeks";
        Console.WriteLine(str1);

        // Give Error Unrecognized escape sequence \H, \G, \p
        // string str3 = "X:\Home\GFG\Geeks.cs";
        // Console.WriteLine(str3);

        // using double slash \\
        string str2 = "X:\\Home\\GFG\\program.cs";
        Console.WriteLine(str2);

    }
}
```

**Output:** 

```cs
GeeksforGeeks
X:\Home\GFG\program.cs
```

**使用串联创建字符串:**我们可以使用 C# 中的字符串串联运算符“+”来创建字符串。要从字符串实例和字符串文字的任意组合创建单个字符串，字符串串联运算符(+)用于组合或合并一个或多个字符串。

*   **程序:**说明字符串连接运算符的使用

## C#

```cs
// C# program to demonstrate the use of
// the string concatenation operator.
using System;
class Geeks {

    // Main Method
    public static void Main()
    {
        string s1 = "Geek";
        string s2 = "s";
        string s3 = "For";
        string s4 = "Geek";

        // using concatenation operator
        string str = s1 + s2 + s3 + s4 + "s";

        Console.WriteLine(str);
    }
}
```

**Output:** 

```cs
GeeksForGeeks
```

**使用** [**构造函数**](https://www.geeksforgeeks.org/c-sharp-constructors/) **创建字符串:**字符串类有几个重载的构造函数，它们接受一个字符或字节数组。一些构造函数包含指向字符数组或有符号字节数组的指针作为参数。

*   **程序:**到说明使用构造函数创建字符串

## C#

```cs
// C# program to demonstrate the creation
// of string using the constructor
using System;
class Geeks {

    // Main Method
    public static void Main()
    {
        char[] chars = { 'G', 'E', 'E', 'K', 'S' };

        // Create a string from a character array.
        string str1 = new string(chars);
        Console.WriteLine(str1);

        // Create a string that consists of
        // a character repeated 20 times.
        string str2 = new string('G', 10);
        Console.WriteLine(str2);

        /* below comment part give the error
           for unsafe mode go through offline
           sbyte[] bytes = { 0x41, 0x42, 0x43,
           0x44, 0x45, 0x00 };
           string stringtoBytes = null;
           string stringtomChars = null;
            unsafe
            {
                fixed (sbyte* pbytes = bytes)
                {

                    // Create a string from a pointer
                    // to a signed byte array.
                    stringFromBytes = new string(pbytes);
                }

                fixed (char* pchars = chars)
                {

                    // Create a string from a pointer
                    // to a character array.
                    stringFromChars = new string(pchars);
                }
            }

            Console.WriteLine(stringtoBytes); // output : ABCDE
            Console.WriteLine(stringtoChars); // output : GEEKS */

    }
}
```

**Output:** 

```cs
GEEKS
GGGGGGGGGG
```

**使用属性或方法创建字符串:**检索属性或调用总是返回字符串的方法。例如，使用字符串类的方法从更大的字符串中提取子字符串。

*   **程序:**说明使用属性或方法创建字符串

## C#

```cs
// C# program to extract a substring from a larger
// string using methods of the String class
using System;
class Geeks {

    // Main Method
    public static void Main()
    {
        string sentence = "Geeks For Geeks";

        // Extract the second word.

        // taking the first space position value
        int startpos = sentence.IndexOf(" ") + 1;

        // taking the second space position value
        int endpos = sentence.IndexOf(" ", startpos) - startpos;

        // now extract second word from the sentence
        string wrd = sentence.Substring(startpos, endpos);

        Console.WriteLine(wrd);
    }
}
```

**Output:** 

```cs
For
```

**使用格式创建字符串:**使用“格式”方法将值或对象转换为其字符串表示形式。*弦。Format* 方法返回一个字符串。

*   **程序:**说明使用 Format 方法创建字符串

## C#

```cs
// C# method to illustrate the creation
// of string using format method
using System;
class Geeks {

    // Main Method
    public static void Main()
    {
        int no = 10;
        string cname = "BMW";
        string clr = "Red";

        // string creation using string.Format method
        string str = string.Format("{0} {1} Cars color " +
                     "are {2}", no.ToString(), cname, clr);
        Console.WriteLine(str);
    }
}
```

**Output:** 

```cs
10 BMW Cars color are Red
```

**字符串类属性:**字符串类有如下两个属性:

1.  **Chars:** 用于获取当前 String 对象中指定位置的 Char 对象。
2.  **长度:**用于获取当前 String 对象中的字符数。要了解更多关于字符串类属性的信息，请访问 C# 中的 [**字符串属性。**](https://www.geeksforgeeks.org/c-string-properties/)