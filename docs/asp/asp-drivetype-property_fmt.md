# ASP 驱动类型属性

> 原文:[https://www.geeksforgeeks.org/asp-drivetype-property/](https://www.geeksforgeeks.org/asp-drivetype-property/)

**ASP 驱动类型属性**用于获取给定驱动的类型。它返回一个介于 0 和 5 之间的数值，指定驱动器的类型，如下所示:

*   **0:** This is for unknown drives.
*   **1:** This is used for removable drives.
*   **2:** This is used to fix the driver.
*   **3:** This is used for network drives.
*   **4:** This is for CD-ROM.
*   **5:** This is for RAM disks.

**语法:**

```vb
DriveObject.DriveType
```

下面的例子说明了 ASP 驱动。驱动类型属性。

**示例 1:** 使用硬盘。

## ASP

```vb
<%
dim fs,dr
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the drive
set dr=fs.GetDrive("d:")

'Getting the type of the drive
Response.Write("The type of the drive is: " & dr.DriveType)

set dr=nothing
set fs=nothing
%>
```