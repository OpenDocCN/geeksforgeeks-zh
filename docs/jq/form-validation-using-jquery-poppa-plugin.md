# 使用 jQuery Poppa 插件进行表单验证

> 原文:[https://www . geesforgeks . org/form-validation-using-jquery-poppa-plugin/](https://www.geeksforgeeks.org/form-validation-using-jquery-poppa-plugin/)

在本文中，我们将学习如何使用 jQuery **Poppa** 插件实现表单验证。这是一个非常容易使用、可靠、跨浏览器友好和轻量级的插件，使得客户端验证非常简单。

**注意:**请下载工作文件夹中的 jQuery [**Poppa**](https://github.com/eceterak/Poppa) 插件，并在你的 HTML 代码头部包含所需文件。

> <link href="”https://fonts.googleapis.com/css?family=Roboto:300,400,700”&nbsp;<br/"> rel= "样式表" type = " text/CSS "/>
> <link href = " https://stack path . bootstrapcdn . com/bootstrap/4 . 1 . 3/CSS/bootstrap . min . CSS "
> rel = "样式表" type = " text/CSS "/>
> <link href = " https://use . font awesome . com/releases/v 5 . 5 . 0/CSS/all . CSS "
> relfamily=Roboto:300，400，700"
> rel= "样式表" type = " text/CSS "/>
> T21】link href = " global . CSS？family=Roboto:300，400，700"
> rel= "样式表" type = " text/CSS "/>
> <link href = " github . CSS？family=Roboto:300，400，700"
> rel= "样式表" type="text/css"/ >
> <脚本 src = " global . js "></脚本>
> <脚本 src = " poppa . js "></脚本>
> 脚本 src = " highlight . js "></脚本>

**示例 1:** 以下示例演示了使用 jQuery **Poppa** 插件的简单表单验证。当给定无效输入时，输出显示有效的验证。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
  <meta name="viewport"
        content="width=device-width, initial-scale=1">
  <title>jQuery form validation Poppa plugin</title>

  <link rel="stylesheet"
        href=
"https://fonts.googleapis.com/css?family=Roboto:300,400,700">

  <!-- Include Bootstrap CSS -->
  <link rel="stylesheet"
        href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css">

  <!-- Include FontAwesome CSS -->
  <link rel="stylesheet"
        href=
"https://use.fontawesome.com/releases/v5.5.0/css/all.css">

  <!-- Include the Poppa Plugin Stylesheets -->
  <link rel="stylesheet" type="text/css" 
        href="validation.css">
  <link rel="stylesheet" type="text/css"
        href="global.css">
  <link rel="stylesheet" type="text/css" 
        href="github.css">
  <style>
    h2 {
      padding-left: 300px;
    }
  </style>
</head>

<body>
  <h2 style="color:green">
    GeeksforGeeks
  </h2>
  <b style="padding-left:300px">
    jQuery form validation Poppa
    plugin
  </b>
  <br><br>
  <div class="container">
    <div class="row">
      <div class="col-9">
        <div class="example-block mb-4">
          <form action="" class="user-registration mb-3">
            <h6 class="title mb-2 mt-0">
              Registration form for User
            </h6>
            <div class="form-group">
              <label>Login ID</label>
              <input name="login" type="text"
                     data-validation-length="min:3" 
                     class="form-control" required>
            </div>
            <div class="form-group">
              <label>Email ID</label>
              <input name="email" type="email"
                     class="form-control" required>
            </div>
            <div class="form-group">
              <label>Password</label>

              <input name="password" type="password"
                     class="form-control" required>
            </div>
            <div class="form-group">
              <label>Website</label>
              <input name="website" data-validation-type="url"
                     class="form-control">
            </div>
            <div class="form-group">
              <label class="mb-0">
                I agree to the terms of service
              </label>
              <input type="checkbox" 
                     data-validation-message=
                     "You have to agree to terms of service"
                     required>
            </div>
            <button type="submit" class="btn btn-primary">
              Submit
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>

  <!-- Include jQuery -->
  <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
  </script>

  <!-- Include the Poppa Plugin Scripts -->
  <script src="global.js"></script>
  <script src="poppa.js"></script>
  <script src="highlight.js"></script>
  <script>
    $(document).ready(function () {

      /** Initiate highlighting */
      hljs.initHighlightingOnLoad();

      /** Initiate validation on each form */
      $('.user-registration').validation({
        'autocomplete': 'off',
        'liveValidation': false
      });
    });
  </script>
</body>
</html>
```