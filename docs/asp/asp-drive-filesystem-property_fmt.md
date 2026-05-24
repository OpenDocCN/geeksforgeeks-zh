# ASP Drive FileSystem 属性

> 原文: [https://www.geeksforgeeks.org/asp-drive-filesystem-property/](https://www.geeksforgeeks.org/asp-drive-filesystem-property/)

`ASP Drive FileSystem` 属性用于返回用于特定驱动器的文件系统的名称。它返回与其文件系统相对应的下列值之一。

*   `Fat`: 用于可移动驱动器。
*   `cdfs`: 用于光驱。
*   `FAT`、`FAT32` 或 `NTFS`: 用于 Windows 2000 或 Windows 操作系统上的硬盘。
*   `fat` 或 `fat32`: 用于 Windows 9x 上的硬盘。

## 语法

```vb
DriveObject.FileSystem
```

## 示例

下面的代码说明了 `ASP Drive FileSystem` 属性。

```vb
<%
dim fs,dr
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the drive to be checked
set dr=fs.GetDrive("d:")

'Getting the file system of the drive
Response.Write("The file system in use is: " & dr.FileSystem)

set dr=nothing
set fs=nothing
%>
```

## 输出

```vb
The file system in use is: NTFS
```