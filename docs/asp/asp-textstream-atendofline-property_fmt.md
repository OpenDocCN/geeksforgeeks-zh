# ASP TextStream.AtEndOfLine 属性

> 原文：[https://www.geeksforgeks.org/asp-textstream-atendofline-property/](https://www.geeksforgeks.org/asp-textstream-atendofline-property/)

`ASP TextStream.AtEndOfLine` 属性用于返回一个布尔值，该值指定文件指针是否位于文本流文件的行尾。如果文件指针位于行尾，则返回 `true`，否则返回 `false`。

**注意：** 此属性仅适用于以阅读模式打开的 `TextStream` 对象。

## 语法

```vb
TextStreamObject.AtEndOfLine
```

### 示例

下面的代码说明了 ASP `AtEndOfLine` 属性。

```vb
<%
dim fs,f,t,x
set fs=Server.CreateObject("Scripting.FileSystemObject")
set f=fs.CreateTextFile("d:\GFG.txt")
f.write("Hello GeeksForGeeks")
f.close

set t=fs.OpenTextFile("d:\GFG.txt",1,false)
do while t.AtEndOfLine<>true
  x=t.Read(1)
loop
t.close
Response.Write("The last character in the line is: " & x)
%>
```

**输出：**

```vb
The last character in the line is s.
```