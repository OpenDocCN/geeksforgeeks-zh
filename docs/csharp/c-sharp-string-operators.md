# C# |字符串运算符

> 原文:[https://www.geeksforgeeks.org/c-sharp-string-operators/](https://www.geeksforgeeks.org/c-sharp-string-operators/)

[字符串](https://www.geeksforgeeks.org/c-string/)是一个字符数组。 [**字符串类**](https://www.geeksforgeeks.org/c-string-class/) 将文本表示为一系列 Unicode 字符，并在**中定义。NET 基类库**。String 类的主要用途是提供属性、运算符和方法，这样使用字符串就变得容易了。
**字符串类中存在两种类型的运算符:**

1.  **等式(字符串，字符串)运算符**
2.  **不等式(字符串，字符串)运算符**

#### 等式(字符串，字符串)运算符

该运算符用于检查给定的字符串是否包含相同的值。如果两个字符串相等，则返回 true。否则，返回 false。
**语法:**

```cs
public static bool operator == ( string x, string y );
```

**参数:**

> **字符串 x:** 字符串 x 是要比较的第一个字符串。
> **字符串 y:** 字符串 y 是第二个要比较的字符串。

**返回值:**该运算符的返回类型为*系统。布尔*。如果字符串 *x* 等于字符串 *y* ，则返回**真**，否则返回**假**。
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// Equality operator
using System;

class GFG {

    // Main Method
    public static void Main(string[] args)
    {

        // variables
        string s1 = "WelcomeToGeeks";
        string s2 = "WelcomeToGeeks";
        string s3 = "Geeksforgeeks";
        bool result1, result2;

        // Equality operator return true
        // as both strings are equal
        result1 = s1 == s2;
        Console.WriteLine("s1 is equal to s2: {0} ", result1);

        // Equality operator return false
        // as both strings are not equal
        result2 = s1 == s3;
        Console.WriteLine("s1 is equal to s3: {0} ", result2);
    }
}
```

**输出:**

```cs
s1 is equal to s2: True 
s1 is equal to s3: False 
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate
// the Equality operator
using System;

class GFG {

    // Main method
    public static void Main()
    {

        // function calling
        Check("GEEKS");
        Check("geeks");
        Check("GEEKS");
    }

    // Function to check the
    // string for equality
    static void Check(String value)
    {

        // string str
        String str = "geeks";

        // Display the comparison between strings
        Console.WriteLine("String 1: {0}", str);
        Console.WriteLine("String 2:  {0}", value);
        Console.WriteLine("Comparison of string 1 and string 2: {0}",
                                                      str == value);
    }
}
```

**输出:**

```cs
String 1: geeks
String 2:  GEEKS
Comparison of string 1 and string 2: False
String 1: geeks
String 2:  geeks
Comparison of string 1 and string 2: True
String 1: geeks
String 2:  GEEKS
Comparison of string 1 and string 2: False
```

#### 不等式(字符串，字符串)运算符

该运算符用于检查给定的字符串是否包含不同的值。如果两个字符串彼此不同，则返回 true。否则，返回 false。
**语法:**

```cs
public static bool operator != ( string x, string y );
```

**参数:**

> **字符串 x:** 字符串 x 是要比较的第一个字符串。
> **字符串 y:** 字符串 y 是第二个要比较的字符串。

**返回值:**该运算符的返回类型为*系统。布尔*。如果*字符串 x* 不等于字符串 y，则返回**真**，否则返回**假**。
下面给出一些例子，以便更好地理解实现:
**例子 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// Inequality operator
using System;

class GFG {

    // Main Method
    public static void Main(string[] args)
    {

        // variables
        string s1 = "WelcomeToGeeks";
        string s2 = "WelcomeToGeeks";
        string s3 = "Geeksforgeeks";
        bool result1, result2;

        // Inequality operator return true
        // as both strings are different from each other
        result1 = s1 != s3;
        Console.WriteLine("s1 is different from s3: {0} ", result1);

        // Inequality operator return false
        // as both strings are equal
        result2 = s1 != s2;
        Console.WriteLine("s1 is different from s2: {0} ", result2);
    }
}
```

**输出:**

```cs
s1 is different from s3: True 
s1 is different from s2: False
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the concept
// of Inequality operator
using System;

class GFG {

    // main method
    public static void Main()
    {

        // function calling
        Check("GEEKS");
        Check("geeks");
        Check("GEEKS");
    }

    // method to check the string value
    static void Check(String value)
    {

        // string str
        String str = "geeks";

        // Display the comparison between strings
        Console.WriteLine("string 1: {0}", str);
        Console.WriteLine("string 2:  {0}", value);
        Console.WriteLine("Comparison of string 1 and string 2: {0}",
                                                       str != value);
    }
}
```

**输出:**

```cs
string 1: geeks
string 2:  GEEKS
Comparison of string 1 and string 2: True
string 1: geeks
string 2:  geeks
Comparison of string 1 and string 2: False
string 1: geeks
string 2:  GEEKS
Comparison of string 1 and string 2: True
```

**参考:**[https://docs.microsoft.com/en-us/dotnet/api/system.string?视图= net framework-4 . 7 . 2 # 操作员](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=netframework-4.7.2# operators)