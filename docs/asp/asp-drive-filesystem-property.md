# ASP 驱动。文件系统属性

> 原文:[https://www . geesforgeks . org/ASP-drive-file system-property/](https://www.geeksforgeeks.org/asp-drive-filesystem-property/)

**ASP 驱动。文件系统属性**用于返回用于特定驱动器的文件系统的名称。它返回与其文件系统相对应的下列值之一。

*   **Fat:** This is for removable drives.
*   **cdfs:** This is for optical drives.
*   **FAT、FAT32** 、**或 NTFS:** 此为 Windows 2000 或 windows 操作系统上硬盘使用。
*   **fat or fat32:** This is the hard disk used on Windows 9x.

**语法:**

```vb
DriveObject.FileSystem
```

**示例:**下面的代码说明了 ASP 驱动。文件系统属性。

## ASP

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

**输出:**

```vb
The file system in use is: NTFS
```