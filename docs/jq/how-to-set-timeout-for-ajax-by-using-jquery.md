# 如何使用 jQuery 为 ajax 设置超时？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery 设置 ajax 超时/](https://www.geeksforgeeks.org/how-to-set-timeout-for-ajax-by-using-jquery/)

在 web 编程中，使用 Ajax 使得结果数据显示在网页的一部分中，而无需重新加载页面。用户需要执行 Ajax 请求，并希望在一个时间范围内得到结果。在这个场景中，代码中使用了 jquery *超时*特性。会话超时是基于 Ajax 的 web 应用程序中非常常见的功能。
在响应界面中，程序员需要在响应之前延迟 ajax 请求来完成一些任务。这可以通过使用 jQuery[**setTimeout()**](https://www.geeksforgeeks.org/java-script-settimeout-setinterval-method/)功能来实现。这个函数在给定的时间后执行给定的 Ajax 代码。
**语法:**

```html
$.ajax(page_url);
```

```html
$.ajax(page_url,[options]);
```

**参数:**

*   **page_url:** 此参数用于提交数据或检索数据。
*   **选项:**此参数用于保存 ajax 请求所需的其他配置设置。

以下示例说明了方法:
**示例 1:**

*   **代码片段:**

```html
$.ajax({
    url: "test.php",
    error: function(){
        //Error code
    },
    success: function(){
        //Success code
    }
   timeout: 5000 // sets timeout to 5 seconds
});
```

*   如果请求成功，则执行**成功**功能。或者有时如果出现错误，快速响应比等待更长时间更好。这在**错误**功能中处理。下面的程序解释了代码 ajax 部分中**超时**选项的实现。**超时**是指定处理请求的时间(以毫秒为单位)的数字。

**节目:**

*   **HTML 文件:**

## 超文本标记语言

```html
<!DOCTYPE html>

<html lang="en">

<head>
    <meta charset="utf-8">
    <title>Set timeout for ajax using jQuery</title>
    <style>
        body {
            width: 450px;
            height: 300px;
            margin: 10px;
            float: left;
        }

        .height {
            height: 10px;
        }
    </style>

    <script src=
"http://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js">
    </script>

    <script language="javascript">
        var ajaxObject = null;

        // ajaxcall function will handle ajax call
        function ajaxCall() {

            var dataquery = 'true';

            if (ajaxObject != null) {
                ajaxObject.abort();
                $("#ajaxOutput")
                .html("Ajax aborted for initialization again! ");
                ajaxObject = null;
            }

            // creating ajax call
            ajaxObject = $.ajax({

                // setting the url
                url: "data.php",

                data: {
                    dataquery: ''
                },

                // Set to 5 seconds for timeout limit
                timeout: 5000,

                //Check for success message in ajaxOutput div
                success: (function(response, responseStatus) {
                    if (responseStatus == 'success') {
                        $("#ajaxOutput").html(response);
                    }
                }),

                // Check for existence of file
                statusCode: {
                    404: function() {
                        $("#ajaxOutput")
                        .html("File does not exists!");
                    }
                },

                // If the time exceeds 5 seconds
                // then throw error message
                error: function(xhr, textStatus, errorThrown) {

                    if (textStatus == 'timeout') {
                        $("#ajaxOutput")
                        .html("Error : Timeout for this call!");
                    }
                }
            });
        }
    </script>
</head>

<body>
    <h1 style="color:green">GeeksforGeeks</h1>
    <b> Set timeout for ajax using jQuery </b>
    <div class="height"> </div>
    <div>
        <button type="button" onclick="ajaxCall()">
          Send Data
        </button>
        <div class="height"> </div>
        <div id="ajaxOutput"> </div>

    </div>

</body>

</html>
```