# 使用等于(==)运算符检查给定字符串是否相等的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序检查给定字符串是否等于运算符/](https://www.geeksforgeeks.org/c-sharp-program-to-check-given-strings-are-equal-or-not-using-equal-to-operator/)

给定两个字符串，我们需要使用==运算符检查它们是否相等。==运算符比较引用标识，即它们是否引用堆中的相同标识。如果它们相等，则返回真，否则返回假。

**示例:**

```cs
Input
String 1 : geeks
String 2 : geeks
Output   : Equal

Input
String 1 : geeks
String 2 : geeqs
Output   : Not Equal
```

**方法:**

> 对于给定的两个字符串，使用==运算符进行比较
> 
> *   如果它返回真，那么字符串是相等的。
> *   如果返回 false，则字符串不相等。

**例 1:**

## C#

```cs
// C# program to check given strings are
// equal or not. Using == operator
using System;

class GFG{

public static void Main()
{
    string str1 = "geeks";
    string str2 = "geeks";

    // Here we use == operator to check
    // the equality of the strings
    Console.WriteLine(str1 == str2);
}
}
```

**Output**

```cs
True
```

**例 2:**

## C#

```cs
// C# program to check given strings
// are equal or not. Using == operator
using System;

class GFG{

public static void Main()
{
    string str1 = "geeks";
    string str2 = "geeqs";

    // Here we use == operator to check
    // the equality of the strings
    Console.WriteLine(str1 == str2);
}
}
```

**Output**

```cs
False
```

但是当我们比较引用标识不同的字符串时，==运算符可能不会像预期的那样工作。让我们借助下面的例子来理解:

## C#

```cs
// C# program to check given strings
// are equal or not. Using == operator
using System; 

class GFG{

static void Main(string[] args) 
{
    object str1 = "geeks";  
    object str2 = new string("geeks");      

    Console.WriteLine(str1 == str2); 
}      
} 
```

**Output**

```cs
False
```