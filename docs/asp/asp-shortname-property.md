# ASP 简称属性

> 原文:[https://www.geeksforgeeks.org/asp-shortname-property/](https://www.geeksforgeeks.org/asp-shortname-property/)

**ASP 短名称属性**用于获取系统上指定文件或文件夹的短名称。

**语法:**

*   **对于文件对象:**

    ```vb
    FileObject.ShortName
    ```

*   **对于文件夹对象:**

    ```vb
    FolderObject.ShortName
    ```

    以下示例说明了 **ASP 短名称属性**。

    **示例 1:** 下面的代码说明了 ASP 文件。短名称属性。

    ## 动态服务器页面

    ```vb
    <%
    dim fs,f
    set fs=Server.CreateObject("Scripting.FileSystemObject")

    'Getting the file
    set f=fs.GetFile("d:\alargefilename.txt")

    'Getting the full name of the file
    Response.Write("Full Name: " & f.Name)

    'Getting the short name of the file
    Response.Write("<br>Short Name: " & f.ShortName)

    set f=nothing
    set fs=nothing
    %>
    ```

    **输出:**

    ```vb
    Full Name: alargefilename.txt
    Short Name: ALARGE~1.TXT
    ```

    **示例 2:** 下面的代码说明了 ASP 文件。短名称属性。

    ## 动态服务器页面

    ```vb
    <%
    dim fs,fol
    set fs=Server.CreateObject("Scripting.FileSystemObject")

    'Getting the folder
    set fol=fs.GetFolder("d:\geeksforgeeksfolder")

    'Getting the full name of the folder
    Response.Write("Full Name: " & fol.Name)

    'Getting the short name of the folder
    Response.Write("<br>Short Name: " & fol.ShortName)

    set fol=nothing
    set fs=nothing
    %>
    ```

    **输出:**

    ```vb
    Full Name: geeksforgeeksfolder
    Short Name: GEEKSF~1
    ```