# jQWidgets jqxFileUpload file inputname 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxfileupload-fileinputname-property/](https://www.geeksforgeeks.org/jqwidgets-jqxfileupload-fileinputname-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。 **jqxFileUpload** 是一个小部件，可以用来选择文件并上传到服务器。

**文件输入名称**属性用于设置或返回隐藏文件输入的名称属性。它接受字符串类型的值，默认值为”。

**语法:**

*   设置*文件输入名称*属性:

    ```html
    $('Selector').jqxFileUpload({ fileInputName : string});
    ```

*   返回*文件输入名称*属性:

    ```html
    var fileInputName = 
        $('Selector').jqxFileUpload('fileInputName');
    ```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link type="”text/css”" rel="”Stylesheet”" href="”jqwidgets/styles/jqx.base.css”">
> <脚本类型=【文本/JavaScript】src =【脚本/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【文本/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> <脚本类型=【文本/JavaScript】src =【jqwidgets/jqxbuttons . js

**示例:**以下示例说明了 jQWidgets 中的 jqxFileUpload**file inputname**属性:

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <link type="text/css" rel="Stylesheet" 
          href="jqwidgets/styles/jqx.base.css" />
    <script type="text/javascript" 
              src="scripts/jquery-1.11.1.min.js">
    </script>
    <script type="text/javascript" 
              src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxbuttons.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxfileupload.js">
    </script>

</head>

<body>
    <h1 style="color: green">
          GeeksforGeeks
    </h1>

    <h3>jQWidgets jqxFileUpload fileInputName property</h3>

    <div id="gfg"></div>

    <script type="text/javascript">
        $(document).ready(function () {
            $('#gfg').jqxFileUpload({ 
                theme: 'energyblue',
                width: 300,
                uploadUrl: 'upload.php',
                fileInputName: 'fileInput'
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/496b7201949f497fd0066d87acee1059.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxfileupload/jquery-file-upload-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxfileupload/jquery-file-upload-api.htm)