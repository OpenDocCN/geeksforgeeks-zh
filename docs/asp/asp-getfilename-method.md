# ASP 获取文件名方法

> 原文:[https://www.geeksforgeeks.org/asp-getfilename-method/](https://www.geeksforgeeks.org/asp-getfilename-method/)

ASP 中的 ***GetFileName 方法是*** 用于返回代表 ASP 文件名称的字符串值。或指定路径中最后一个组件的文件夹。

**语法:**

```vb
***FileSystemObject.GetFileName(path)*** 
```

***参数值:***

***路径:*** 是必选属性。它指定特定文件的绝对或相对路径。

***示例代码:*** 下面的示例说明了 ASP 获取文件名的方法。

## Javascript

```vb
<%
dim fs,p
set fs=Server.CreateObject("Scripting.FileSystemObject")
p=fs.getfilename("d:\sudo\GFG.html")
response.write(p)
set fs=nothing
%>
```

***输出:***

```vb
***GFG***
```