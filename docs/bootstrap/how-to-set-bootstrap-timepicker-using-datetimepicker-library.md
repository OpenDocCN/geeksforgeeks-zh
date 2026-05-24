# 如何使用 datetimepicker 库设置 Bootstrap Timepicker？

> 原文:[https://www . geeksforgeeks . org/how-set-bootstrap-time picker-use-datetime picker-library/](https://www.geeksforgeeks.org/how-to-set-bootstrap-timepicker-using-datetimepicker-library/)

在本文中，我们将看到如何使用引导数据库日期选择器插件来实现日期选择器，以便使用 jQuery 选择日期和时间。默认情况下，选择今天的日期。DateTimePicker 有各种可配置的选项，可以根据需要使用 DateTimePicker。在本教程中，我们将看到如何使用引导数据库日期选择器插件来选择日期和时间来实现日期选择器。

**DateTimePicker 有以下视图:**

*   十年视图
*   年度视图
*   月视图
*   日视图
*   小时视图
*   带子午线的日景
*   带子午线的小时视图

**DateTimePicker 可以通过以下方式进行格式化:**

*   yyyy-mm-dd
*   yyy-mm-dd hh:ii
*   yyyy-mm-ddThh：ii
*   yyy-mm-dd hh:ii:ss
*   yyyy-mm-ddThh:ii:ssZ

**DateTimePicker 格式** : 默认格式为字符串‘mm/DD/yyyy’。

<figure class="table">T32】显示一个月中的某一天T36】T38**M**显示一个月，不带前导零T82】以小写

| format | explain | Example (6/7/2021 06:02:09) |
| --- | --- | --- |
| **d** | Displays the day of the month without leading zeros. | six |
| 【T29】DD | Fr |
|  | Display year in two-digit format- | Twenty-one |
| **YYYY** | Displays the year in four-digit format. | Two thousand and twenty-one |
| **A** | AM【T88 | Displays the number of seconds with leading zeros. | 09 |
| **米** | Displays the number of packets without leading zeros. | Two |
| **毫米** | Displays the number of packets with leading zeros. |  |

</figure>

### **设置日期选择器:**

**第一步:在所有其他样式表加载我们的 CSS 之前，将 Bootstrap 和 jQuery CDN 包含到你的<头>中。**

> <src 脚本= " https://Ajax . Google APIs . com/Ajax/libs/jquery/1 . 9 . 1/jquery . js "></script><src 脚本= " https://maxcdn . bootstracdn . com/bootstrap/3 . 3 . 6/js/中

**第二步:在引导 CSS CDN 之后包含 DateTimePicker JS 和 CSS CDN。**

> <链接 href = " https://cdnjs . cloudflare . com/Ajax/libs/bootstrap-date picker/4 . 17 . 37/CSS/bootstrap-date picker . min . CSS " rel = " style sheet "
> <脚本 src = " https://cdnjs . cloudflare . com/Ajax/libs/bootstrap

**第三步:将下面的代码包含在<正文>中，接受用户的时间。**

```html
<div class="container" style="margin: 50px">  
   <div style="position: relative">  
       <input class="form-control" type="text" id="time"/>  
   </div>  
</div>  
```

**注意:** DateTimePicker 组件应始终放置在相对定位的容器中。

**第四步:在<正文>标签后添加<脚本>标签中的以下 JavaScript，指定“HH:mm:ss”格式为 DateTimePicker。**

```html
$('#time').datetimepicker({
    format: 'yyyy-mm-dd'
});
```

**注:**可根据需要指定自定义格式。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>DateTimepicker</title>

    <!-- Include Bootstrap CDN -->
    <link href=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css"
        rel="stylesheet">
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.js">
    </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js">
    </script>

    <!-- Include Moment.js CDN -->
    <script type="text/javascript" src=
"https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.9.0/moment.min.js">
    </script>

    <!-- Include Bootstrap DateTimePicker CDN -->
    <link
        href=
"https://cdnjs.cloudflare.com/ajax/libs/bootstrap-datetimepicker/4.17.37/css/bootstrap-datetimepicker.min.css"
        rel="stylesheet">

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/bootstrap-datetimepicker/4.17.37/js/bootstrap-datetimepicker.min.js">
        </script>
</head>

<body>

    <!-- Include datetime input to display
        datetimepicker in container with
        relative position -->
    <div class="container" style="margin:100px">
        <div style="position: relative">

            <!-- Include input field wiht id so
                that we can use it in JavaScript
                to set attributes.-->
            <input class="form-control"
                type="text" id="datetime" />
        </div>
    </div>

    <script>

        // Below code sets format to the
        // datetimepicker having id as
        // datetime
        $('#datetime').datetimepicker({
            format: 'hh:mm:ss a'
        });
    </script>
</body>

</html>
```

### 输出:

![](img/c94800dcc1b143effa886f8ded56272e.png)