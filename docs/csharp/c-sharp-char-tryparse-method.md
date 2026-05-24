# C# | Char。锥虫()法

> 原文:[https://www.geeksforgeeks.org/c-sharp-char-tryparse-method/](https://www.geeksforgeeks.org/c-sharp-char-tryparse-method/)

在 C# 中， ***Char。*** 是 Char 类方法，用于将给定字符串的值转换为其等效的 Unicode 字符。其性能优于 ***Char。Parse()* 方法。**

****语法:****

```cs
public static bool TryParse(string str, out char result) 
```

****参数:****

> ***   **str:** is the *system. String* type parameter, which can contain *single character* or *null value* .*   **Result:** This is an uninitialized parameter, which is used to store the equivalent Unicode character when the conversion is successful, or an undefined value if the conversion fails. The type of this parameter is *system. Char* 。**

****返回类型:**方法返回**真**，如果成功转换字符串，否则返回**假。**所以这种方法的类型是*系统。布尔*。**

****注意:**当**串**为**空**或**长度**等于 1 则转换失败。

**例 1:** 下面是演示 *Char 用法的程序。*方法。**

```cs
// C# program to illustrate the
// Char.TryParse () Method
using System;

 class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;
        Char value;

        // Input Capital letter A
        result = Char.TryParse("A", out value);

        // Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());

        // Input Capital letter Z
        result = Char.TryParse("Z", out value);

        // Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());

        // Input Symbol letter
        result = Char.TryParse("{content}quot;, out value);

        // Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());

        // Input number
        result = Char.TryParse("100", out value);

        // Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());

        // Input small letter z
        result = Char.TryParse("z", out value);

        // Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());
    }
}
```

****Output:**

```cs
True
A
True
Z
True
$
False

True
z

```** 

****示例 2:** 下面是一个演示*字符使用的程序。TryParse()* 输入不是单个字符并以符号开头的方法。**

```cs
// C# program to illustrate the
// Char.TryParse () Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;
        Char value;

        // Input is  String return false
        result = Char.TryParse("GeeksforGeeks", out value);

        // Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());

        // Input letter start with symbol  <
        result = Char.TryParse("<N", out value);

        // Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());
    }
}
```

****Output:**

```cs
False

False

```**