# ASP OpenAsTextStream 方法

> 原文:[https://www.geeksforgeeks.org/asp-openastextstream-method/](https://www.geeksforgeeks.org/asp-openastextstream-method/)

**ASP OpenAsTextStream 方法**用于通过打开指定的文件返回一个 TextStream 对象。它可以用来对文件执行某些操作。

**语法:**

```vb
FileObject.OpenAsTextStream(mode, format)
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Mode:** Specify the file opening mode. It contains three constant values to perform operations on files.
    *   **for reading (1):** This will open the file for reading. Files cannot be written in this mode.
    *   **for writing (2):** This will open the file for writing.
    *   **for appending (8):** This will open the file with the content appended to the end.
*   **Format:** Optional attribute. It contains three constant values, which are used to define the file format.
    *   **tristate false (0):** This opens the file to ASCII. This is the default format.
    *   **Tri-state (1):** This opens the file as Unicode.
    *   **Three-state default (2):** This will use the system default value to open the file.

**示例:**下面的代码演示了 ASP 文件。OpenAsTextStream 方法。

## ASP

```vb
<%
dim fs,f,ts
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the file to be read
Set f=fs.GetFile("d:\GFG.txt")

'Opening the file as a text stream
'in writing mode (2)
Set ts=f.OpenAsTextStream(2)

'Writing some content to the file'
ts.Write("This is a GeeksforGeeks example")

'Closing the stream
ts.Close

'Opening the file as a text stream
'in reading mode (1)
Set ts=f.OpenAsTextStream(1)

'Reading the contents of the file
Response.Write(ts.ReadAll)

'Closing the stream
ts.Close

set ts=nothing
set f=nothing
set fs=nothing
%>
```

**输出:**

```vb
This is a GeeksforGeeks example
```