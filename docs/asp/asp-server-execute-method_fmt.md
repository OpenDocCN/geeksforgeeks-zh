# ASP Server.Execute 方法

> 原文: [https://www.geeksforgeeks.org/asp-server-execute-method/](https://www.geeksforgeeks.org/asp-server-execute-method/)

`Server.Execute` 方法用于从 ASP 文件中执行各种 ASP 脚本。这种方法非常类似于某些编程语言中的过程调用方法。

## 语法

```vb
Server.Execute(path)
```

## 参数值

*   `Path`: 存储一个字符串值，表示要执行的 `.asp` 文件的位置。

## 示例代码

**Sudo.asp**

```vb
<%
response.write("Geeks For Geeks!<br>")
%>
```

**GFG.asp**

```vb
<%
response.write("Welcome to <br>")
Server.Execute("file2.asp")
%>
```

## 输出

```vb
Welcome to
GeeksFoeGeeks
```