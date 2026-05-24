# 字符串和 C# 中字符串的区别

> 原文:[https://www . geesforgeks . org/c-sharp 中字符串与字符串的区别/](https://www.geeksforgeeks.org/difference-between-string-and-string-in-c-sharp/)

[字符串](https://www.geeksforgeeks.org/c-sharp-string-class/)是 System 的别名。字符串类，而不是编写系统。字符串一可以使用字符串，它是系统的简写。字符串类，并在。NET 基类库。内存中 String 对象的大小是 2GB，这是一个不可变的对象，一旦声明，我们就不能修改字符串中的字符，但是我们可以完全删除它

**语法:**

```cs
String variable = "my string";
```

**示例:**

## C#

```cs
// C# program to illustrate String
using System;

class GFG{

public static void Main()
{

    // Declare String variable
    String b = "Welcome to GeeksforGeeks";

    // Display the result
    Console.WriteLine(a);
}
}
```

**输出**:

```cs
Geeks
```

一个[字符串](https://www.geeksforgeeks.org/c-sharp-string/)是一个从 U+0000 到 U+FFFF 的 Unicode 字符序列。或者我们可以说字符串代表文本。它是一个关键字，并且是不可变的，这意味着一旦声明，我们就不能修改字符串中的字符，但是我们可以将其完全删除。我们可以使用以下语法创建一个字符串变量:

**语法:**

```cs
string variable = "my string";
```

**示例:**

## C#

```cs
// C# program to illustrate string
using System;

class GFG{

public static void Main()
{

    // Declare string variable
    string a = "GeeksforGeeks";

    // Display the result
    Console.WriteLine(a);
}
}
```

**输出:**

```cs
GeeksforGeeks
```

**弦与弦的区别**

<figure class="table">

| 

**弦**

 | 

**弦**

 |
| --- | --- |
| 它是一个用于访问字符串变量和格式化方法的类。 | 这是一个用于创建字符串变量的关键字 |
| 我们必须从系统中导入字符串。字符串模块。 | 不需要为字符串导入任何模块 |
| 它是一种数据类型 | 这是一个关键词 |
| 它包含不同类型的方法、属性等。 | 它只是系统的别名。线 |

</figure>