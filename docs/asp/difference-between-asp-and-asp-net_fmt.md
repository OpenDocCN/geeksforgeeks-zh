# ASP 和 ASP.NET 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-asp-and-asp-net/](https://www.geeksforgeeks.org/difference-between-asp-and-asp-net/)

## ASP

ASP 代表**活动服务器页面**。它是一个用于构建网页的开发框架。ASP 是微软在 1998 年推出的第一个服务器端脚本语言。ASP 页面的文件扩展名为`.asp`，通常用 VBScript 编写。它是制作动态网页的一个古老但仍然强大的工具。ASP 是一种在 web 服务器上执行脚本的技术（很像 PHP）。

**例：**

```vb
<!DOCTYPE html>
<html>

<body>
    <%response.write("Welcome to GeeksforGeeks!")%>
</body>

</html>
```

**输出：**

```vb
Welcome to GeeksforGeeks!
```

## ASP.NET

ASP.NET 于 2002 年由微软发布，作为 ASP 的继承者。它也是一个服务器端 web 框架，开源的，是为动态网页的生成而设计的。ASP.NET 网页的文件扩展名是`.aspx`，通常用 C# (C sharp) 编写。ASP.NET 的最新版本是 ASP.NET 4.6。

**例：**

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

**输出：**

```vb
Welcome to GeeksforGeeks!
```

## ASP 和 ASP.NET 的区别

| 动态服务器页面 | ASP.NET |
| --- | --- |
| ASP 是解释型语言。 | ASP.NET 是编译型语言。 |
| ASP 使用 ADO (ActiveX Data Objects) 技术来连接和操作数据库。 | ASP.NET 使用`ADO.NET`来连接和使用数据库。 |
| ASP 是部分面向对象的。 | ASP.NET 是完全面向对象的。 |
| ASP 页面的文件扩展名是`.asp`。 | ASP.NET 页面的文件扩展名是`.aspx`。 |
| ASP 没有继承的概念。 | ASP.NET 可以继承代码中编写的类。 |
| ASP 页面使用脚本语言。 | ASP.NET 使用成熟的编程语言。 |
| ASP 中的错误处理非常差。 | ASP.NET 的错误处理非常好。 |
| ASP 最多有四个内置类，即 request 类、response 类、session 类和 application 类。 | ASP.NET 中有超过 2000 个内置类。 |