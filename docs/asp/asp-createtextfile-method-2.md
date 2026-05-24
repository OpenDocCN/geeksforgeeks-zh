# ASP CreateTextFile()方法

> 原文:[https://www.geeksforgeeks.org/asp-createtextfile-method-2/](https://www.geeksforgeeks.org/asp-createtextfile-method-2/)

**ASP 创建文本文件方法**用于在当前文件夹或目录中创建新的文本文件。它返回一个可用于对文件执行操作的文本流对象。

**语法:**

*   **对于文件夹对象:**

    ```vb
    FolderObject.CreateTextFile(filename, overwrite, unicode)
    ```

*   **文件系统对象:**

    ```vb
    FileSystemObject.CreateTextFile(filename, overwrite, unicode)
    ```

**参数:**该属性有三个参数，如上所述，描述如下:

*   **文件名:**指定新创建的文本文件的名称。
*   **覆盖:**它包含一个布尔值，指示是否可以覆盖现有文件。true 值表示文件可以被覆盖，false 值表示不允许覆盖。默认值为真。这是一个可选参数。
*   **unicode:** 它包含一个布尔值，指示文件是作为 unicode 还是 ASCII 文件创建的。true 值表示文件是作为 Unicode 文件创建的，false 值表示文件是作为 ASCII 文件创建的。默认值为假。这是一个可选参数。

以下示例演示了 **ASP 创建文本文件方法**。

**示例 1:** 下面的示例演示了 ASP 文件夹。创建文本文件方法。

## 动态服务器页面

```vb
<%
dim fs,fo,tfile
Set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the folder where the file has to be created
Set fo=fs.GetFolder("d:\GFG")

'Creating a new text file
Set tfile=fo.CreateTextFile("GFG.txt",false)

'Writing a line to the file
tfile.WriteLine("Hello Geeks!")

'Closing the file
tfile.Close

Response.write("A new textfile has been created!")

'Reading the new text file
Set tfile=fs.OpenTextFile("d:\GFG\GFG.txt", 1)
Response.Write("<br>The File Contents are: " & tfile.ReadAll)
tfile.Close

set tfile=nothing
set fo=nothing
set fs=nothing
%>
```

**输出:**

```vb
A new textfile has been created!
The File Contents are: Hello Geeks! 
```

**示例 2:** 下面的示例演示了 ASP 文件系统对象。创建文本文件方法。

## 动态服务器页面

```vb
<%
dim fs,txtfile
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Creating the text file at the given path
set txtfile=fs.CreateTextFile("D:\gfg.txt")

'Writing a line to the file
txtfile.WriteLine("Hello World!")

'Closing the file
txtfile.Close

Response.Write("The new text file has been created!")

'Reading the new text file
Set txtfile=fs.OpenTextFile("d:\GFG.txt", 1)
Response.Write("<br>The File Contents are: " & txtfile.ReadAll)
txtfile.Close

set txtfile=nothing
set fs=nothing
%>
```

**输出:**

```vb
The new text file has been created!
The File Contents are: Hello World!
```