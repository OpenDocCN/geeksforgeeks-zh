# c# 中字符串转换为整数的不同方式

> 原文:[https://www . geesforgeks . org/different-way-to-convert-string-to-integer-in-c-sharp/](https://www.geeksforgeeks.org/different-ways-to-convert-string-to-integer-in-c-sharp/)

像其他编程语言一样，在 C# 中，我们可以将字符串转换为 int。有三种方法可以转换它，如下所示:

*   使用解析方法
*   使用锥虫法
*   使用从(*系统的转换方法。转换*类)

输入字符串可以是任何类似【10.10”、“10.10”、“10GeeksforGeeks”、“(您的字符串可以是数字、字符组合或空字符串)。
当给定的字符串是数字或浮点数时，我们可以直接使用上面列出的任何方法将其从字符串转换为 int，但是字符和空字符串的组合会引发错误，需要使用异常处理来捕捉。

### 1.使用解析方法

这里，我们正在计算圆的面积，但是给定的输入长度是字符串格式，因此使用了 *[Int32。Parse()](https://www.geeksforgeeks.org/int32-parsestring-method-in-c-sharp-with-examples/)* 方法将长度从字符串转换为 int(等效的 32 位有符号整数)。

```cs
// C# program to convert string to 
// integer using Parse Method
using System;

namespace GeeksforGeeks {

class GFG{

    // Main Method
    public static void Main(string[] args)
    {

        // Taking a string
        string l = "10";

        // using the Method
        int length = Int32.Parse(l);

        // Finding the area of a square
        int aofs = length * length; 

        Console.WriteLine("Area of a circle is: {0}", aofs);
    }
}
}
```

**输出:**

```cs
Area of a circle is: 100

```

**当我们有一个大于整数的值时:**如果您将值大值赋给字符串，那么它将通过*overowexception*处理，因为 int 数据类型不能处理大值(这在很大程度上取决于数据类型的范围)。

```cs
string l="10000000000";
```

输出将是`System.OverflowException: Value was either too large or too small for an Int32.`

**当我们有空字符串时:**如果您保持字符串为空，那么当输入为空时，它将通过异常系统格式异常。

```cs
string l="";
```

输出将是:*系统。格式异常:输入字符串的格式不正确。*

### 2.使用锥虫法

这里，我们使用了 TryParse()方法，Parse()和 TryParse()方法的区别只是 TryParse()方法总是返回它永远不会抛出异常的值。如果你仔细观察一个输入的值，那么它清楚地表明它会抛出一个异常，但是 *TryParse()* 永远不会抛出异常。因此输出为零。

```cs
// C# program to convert string to 
// integer using TryParse Method
using System;

namespace GeeksforGeeks {

class GFG{

    // Main Method
    public static void Main(string[] args)
    {

        // Taking a string
        string l = "10000000000";
        int length = 0;

        // using the method
        Int32.TryParse(l, out length);

        // Finding the area of a square
        int aofs = length * length; 

        Console.WriteLine("Area of a circle is: {0}", aofs);
    }
}
}
```

**输出:**

```cs
Area of a circle is: 0
```

### 3.使用转换方法

这里，我们使用了 *Convert。ToInt32()* 方法，解析()和*转换的区别。to t32()*方法只在于*转换。ToInt32()* 方法总是接受空值返回它。因此输出为零。我们在这个例子中使用了异常处理，因此，如果发生了异常，try 块将抛出异常，catch 块将接受异常并写入任何发生的异常。

```cs
// C# program to convert string to 
// integer using Convert Method
using System;

namespace GeeksforGeeks {

class GFG {

    // Main Method
    public static void Main(string[] args)
    {

        // Taking a string
        string l = null;
        try {
               int length = Convert.ToInt32(l);

               // Finding the area of a square
               int aofs = length * length; 

               Console.WriteLine("Area of a circle is: {0}", aofs);
        }
        catch (Exception e) {
            Console.WriteLine("Unable to convert:Exception:" + e.Message);
        }
    }
}
}
```

**输出:**

```cs
Area of a circle is: 0

```