# jQuery | Filer 插件

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-filer 插件/

jQuery 提供了一个快速的 **jQuery Filer** 上传器插件，方便文件上传的实现。它提供了即时上传文件、文件追加、文件删除、多重选择、拖放支持以及其他文件验证等功能。

请[下载](https://github.com/seblejeune/jquery.filer)所需文件，将其包含在您的工作文件夹中，并包含在标题部分，如下例所示。程序员可以根据工作文件夹中的组织调整代码中的所有文件路径。
**注意:** HTML 输入控件 id 给出为“filer_input”和“filer_input2”以匹配插件的 **custom.js** 代码。

**示例 1:** 在下面的示例中，使用 **jQuery 展示了基本的文件上传实现。文件管理器**插件。程序员可以根据项目需求尝试其他功能。

## 超文本标记语言

```html
<!DOCTYPE>
<html lang="html">

<head>
    <meta http-equiv="Content-Type"
        content="text/html; charset=utf-8" />
    <title>jQuery Filer Plugin</title>

    <!-- Google Fonts -->
    <link href=
"https://fonts.googleapis.com/css?family=Roboto+Condensed"
        rel="stylesheet">

    <!-- Styles -->
    <link href="jquery.filer.css" rel="stylesheet">

    <!-- Javascript -->
    <script src="http://code.jquery.com/jquery-3.1.0.min.js"
            crossorigin="anonymous">
    </script>

    <script src="jquery.filer.min.js"
            type="text/javascript">
    </script>
    <script src="custom.js" type="text/javascript"></script>

    <style>
        body {
            font-family: sans-serif;
            font-size: 14px;
            line-height: 1.5;
            color: #47505d;
            background-color: #ffffff;
            margin: 0;
            padding: 18px;
        }
    </style>
</head>

<body>
    <h1 style="color:green">GeeksForGeeks</h1>
    <b>jQuery Filer Plugin</b>

<p></p>

    <div id="content">

        <!-- File upload form -->
        <form action="upload_form.php" method="post"
                enctype="multipart/form-data">

            <input type="file" name="files[]"
                id="filer_input" multiple="multiple">

            <input type="submit" value="Submit">
        </form>
        <!-- end of File upload-->

    </div>
</body>

</html>
```

**上例使用的 jQuery 代码:**下面的代码 **custom.js** 文件由 **jQuery 提供。文件管理器**插件。

## java 描述语言

```html
$(document).ready(function() {

    $('#filer_input').filer({
        showThumbs: true,
        addMore: true,
        allowDuplicates: false
    });
});
```

**输出:**

![](img/55f5532f6c51ca20b51481a14c484e0d.png)

**注意:**根据程序员给出的上传文件路径，可以在“上传”文件夹中看到上传的文件。

**示例 2:** 在以下示例中，显示了拖放功能。所选文件在底部预览，状态为成功。

## 超文本标记语言

```html
<!DOCTYPE>
<html lang="html">

<head>
    <meta http-equiv="Content-Type"
        content="text/html; charset=utf-8" />

    <title>jQuery Filer DragnDrop Images</title>

    <!-- Google Fonts -->
    <link href=
"https://fonts.googleapis.com/css?family=Roboto+Condensed"
        rel="stylesheet">

    <!-- Styles -->
    <link href="jquery.filer.css" rel="stylesheet">
    <link href="jquery.filer-dragdropbox-theme.css"
            rel="stylesheet">

    <!-- Javascript -->
    <script src="http://code.jquery.com/jquery-3.1.0.min.js"
        crossorigin="anonymous">
    </script>

    <script src="jquery.filer.min.js"
        type="text/javascript">
    </script>

    <script src="custom.js" type="text/javascript"></script>

    <style>
        body {
            margin: 0;
            text-align: center;
            font-family: sans-serif;
            font-size: 16px;
            line-height: 1.5;
            color: #47505d;
            padding: 18px;
            background-color: #ffffff;
            margin: 0;
        }

        .jFiler {
            font-family: inherit;
        }
    </style>
</head>

<body>
    <h1 style="color:green">GeeksForGeeks</h1>
    <b>jQuery Filer Plugin</b>

<p></p>

    <div id="content">

        <!-- For drag and drop of images -->
        <input type="file" name="files[]"
            id="filer_input2" multiple="multiple">
        <!-- end of drag and drop of images  -->

    </div>
</body>

</html>
```

**上例中使用的 jQuery 代码:**[**自定义. js**](https://gerardbalaoro.github.io/jQuery.filer/) 文件由 **jQuery 提供。文件管理器**插件。

**输出:**

![](img/be7520245feeba229c01fe556113e276.png)