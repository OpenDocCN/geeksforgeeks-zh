# 字符串和 String 在 C# 中的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-string-and-string-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-string-and-string-in-c-sharp/)

[`String`](https://www.geeksforgeeks.org/c-sharp-string-class/) 是 `System.String` 类的别名，而不是编写 `System.String`。你可以使用 `string`，它是 `System.String` 类的简写，并且存在于 .NET 基类库中。内存中 `String` 对象的大小限制是 2GB，它是一个不可变的对象，一旦声明，我们就不能修改字符串中的字符，但是我们可以完全删除它。

**语法:**

```cs
String variable = "my string";
```

**示例:**

```cs
// C# program to illustrate String
using System;

class GFG{

    public static void Main()
    {

        // Declare String variable
        String b = "Welcome to GeeksforGeeks";

        // Display the result
        Console.WriteLine(b);
    }
}
```

**输出:**

```cs
Welcome to GeeksforGeeks
```

一个 [`string`](https://www.geeksforgeeks.org/c-sharp-string/) 是一个从 U+0000 到 U+FFFF 的 Unicode 字符序列。或者我们可以说 `string` 代表文本。它是一个关键字，并且是不可变的，这意味着一旦声明，我们就不能修改字符串中的字符，但是我们可以将其完全删除。我们可以使用以下语法创建一个 `string` 变量:

**语法:**

```cs
string variable = "my string";
```

**示例:**

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

## String 与 string 的区别

| **String** | **string** |
| --- | --- |
| 它是一个用于访问字符串变量和格式化方法的类。 | 这是一个用于创建字符串变量的关键字。 |
| 我们必须导入 `System.String` 模块。 | 不需要为 `string` 导入任何模块。 |
| 它是一种数据类型。 | 这是一个关键字。 |
| 它包含不同类型的方法、属性等。 | 它只是 `System.String` 的别名。 |