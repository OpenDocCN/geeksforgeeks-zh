# ASP 和 ASP.NET 的区别

> 原文:[https://www . geesforgeks . org/ASP 和 asp-net 的区别/](https://www.geeksforgeeks.org/difference-between-asp-and-asp-net/)

**ASP:** ASP 代表**活动服务器页面**。它是一个用于构建网页的开发框架。ASP 是微软在 1998 年推出的第一个服务器端脚本语言。ASP 页面的文件扩展名为。asp 和通常用 VBScript 编写。它是制作动态网页的一个古老但仍然强大的工具。ASP 是一种在 web 服务器上执行脚本的技术(很像 PHP)。

**例:**

```vb
<!DOCTYPE html>
<html>

<body>
    <%response.write("Welcome to GeeksforGeeks!")%>
</body>

</html>                    
```

**输出:**

```vb
Welcome to GeeksforGeeks!
```

**ASP。NET:**ASP.NET 于 2002 年由微软发布，作为 ASP 的继承者。它也是一个服务器端 web 框架，开源的，是为动态网页的生成而设计的。ASP.NET 网页的文件扩展名是。aspx 和通常用 C# (C sharp)编写。ASP.NET 的最新版本是 ASP.NET 4.6。

**例:**

```vb
@{ 
    var rank = 50;
}
<html>
<body>
@if (rank < 60)
{
    <p>Welcome to GeeksforGeeks!</p>
}
</body>
</html>
```

**输出:**

```vb
Welcome to GeeksforGeeks!
```

**ASP 和 ASP 的区别。NET:**

| 动态服务器页面 | ASP.NET |
| --- | --- |
| ASP is the interpreted language. | ASP.NET is a compilation language. |
| ASP uses [T9 T9】 ADO (ActiveX Data Objects) technology to connect and cooperate with the database. | ASP.NET uses **ADO.NET** to connect and use the database. |
| ASP is partially object-oriented. | ASP.NET is completely object-oriented. |
| ASP Pages has a file extension **. asp** 。 | The ASP.NET page has the file extension **. aspx** 。 |
| ASP has no concept of inheritance. | ASP.NET inherits the classes written in code later. |
| ASP pages use scripting language. | ASP.NET uses a full-fledged programming language. |
| The error handling in ASP is very poor. | ASP.NET's error handling is very good. |
| ASP has at most four built-in classes, namely request class, response class, session class and application class. | There are more than 2,000 built-in classes in ASP.NET. |