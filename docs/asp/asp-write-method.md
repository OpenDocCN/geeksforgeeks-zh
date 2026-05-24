# ASP Write()方法

> 原文:[https://www.geeksforgeeks.org/asp-write-method/](https://www.geeksforgeeks.org/asp-write-method/)

**ASP Write()方法**用于在网页上显示一个字符串作为输出。这是一种预定义的**响应和文本流**类型对象的方法。

**语法**:

**响应对象:**

```vb
Response.Write variant
```

**对于文本流对象:**

```vb
Textstream.write(string)
```

**参数值:**此方法包含值，即**变量**，它代表您想要显示为输出的指定字符串。

**返回值:**该方法不返回值。

**示例:**下面的代码说明了 **ASP Write()方法**

## 动态服务器页面

```vb
<%
response.write("<h1>ASP Write() Method</h2>")
response.write("
<p>Hello GeeksForGeeks)</p>
")
%>
```

**例 2:**

## 动态服务器页面

```vb
<%
name="GeeksForGeeks"
Response.Write(name)
%>
```

**示例-3:** 下面的代码说明了 ASP 编写方法。

## 动态服务器页面

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")
set f=fs.CreateTextFile("d:\GFG.txt",true)
f.write("Hello GeeksForGeeks")
f
f.close
set f=nothing
set fs=nothing
%>
```

**输出**

```vb
Hello GeeksForGeeks
```