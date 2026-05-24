# ASP 复制文件法

> 原文: [https://www.geeksforgeeks.org/asp-copyfile-method/](https://www.geeksforgeeks.org/asp-copyfile-method/)

ASP 复制文件方法用于将一个或多个文件从一个地方复制到另一个地方。它是文件系统对象的预定义方法。

## 语法

```vb
FileSystemObject.CopyFile source,destination[,overwrite]
```

## 参数值

*   `Source`: 必需的属性。它包含一个字符串文件，其中可以包含通配符，用于指定要复制的一个或多个文件。
*   `Destination`: 也是一个必需的属性。它指定将字符串值复制到文件的位置。它不包含通配符。
*   `Overwrite`: 包含一个布尔值，指示是否可以覆盖现有文件。如果为 `true`，文件将被覆盖；如果为 `false`，则不会。默认值为 `true`。请注意，如果目标设置了只读属性，无论 `overwrite` 值如何，复制文件都将失败。

## 示例代码

下面的示例演示了复制文件方法。

```vb
<%
dim gfg
set gfg=Server.CreateObject("Scripting.FileSystemObject")
gfg.CopyFile "c:\Folder1\A\*.txt","c:\Folder2\"
response.write("File is Copied")
set gfg=nothing
%>
```

## 输出

```vb
File is Copied
```