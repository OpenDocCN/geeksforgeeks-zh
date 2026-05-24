# 如何编辑 Bootstrap 4 日期输入值？

> 原文:[https://www . geesforgeks . org/如何编辑-引导-4-日期-输入-值/](https://www.geeksforgeeks.org/how-to-edit-bootstrap-4-date-input-value/)

我们将了解如何编辑 Bootstrap 4 日期输入值。任务是在简单的 JavaScript 代码的帮助下更改日期字段的值。

**方法:**我们将使用三种网络技术，即 HTML、JavaScript 和 CSS。一般我们选择一些随机值，点击“提交”按钮，它会自动调用一个名为 *edit()* 的嵌入式 JavaScript 函数。在函数中，我们将从“日(dd)”、“月(mm)”、“年(yy)”三个不同的字段中检索值，并将这些值分别存储在三个不同的变量中，如 *d* 、 *m* 、 *y* 。下一步是检查 *d* 和 *m* 的长度是否等于 1，如果是，那么我们要在这些变量前追加一个‘0’。最后，我们必须形成一种格式，即[yyyy-mm-dd]，并相应地更改日期字段的值。

**步骤:**

1.  Retrieve the values of different fields, such as' DD',' MM' and' YY'.
2.  Stores the values of different variables in string format.
3.  Check whether the length of day and month variables is equal to 1.
4.  If the length of the day and month variable is equal to 1, then attach a 0 in front of it, so that the length becomes 2.
5.  Build a date format similar to [yyyy-mm-dd].
6.  Replace the date format with bootstrap *date* field.

## HTML

```html

<!DOCTYPE html>
<html>

<head>

    <!--CDN of Bootstrap-->
    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.6/css/bootstrap.min.css"
        integrity=
"sha384-rwoIResjU2yc3z8GV/NPeZWAv56rSmLldC3R/AZzGRnGxQQKnKkoFVhFQhNUwEyJ"
        crossorigin="anonymous">

    <!--CDN of google font-->
    <style>
        @import url(
'https://fonts.googleapis.com/css2?family=Roboto+Slab:wght@500&display=swap');

        @import url(
'https://fonts.googleapis.com/css2?family=Roboto+Slab:wght@300;500&display=swap');

        .form-control {
            display: inline-block;
            vertical-align: middle;
            float: none;
        }
    </style>
</head>

<body style="border:4px solid rgb(0, 128, 28);">
    <div align="center" class="container">
        <form>
            <h1 style="font-family:'Roboto Slab',serif;
                text-align:center;color:green;">
                GeeksForGeeks
            </h1>

            <br>
            <div align="center">
                <div style="font-family:'Roboto Slab',serif;
                    color:rgb(255, 38, 0);text-align:center;"
                    id="name">
                    Bootstrap Date Field
                </div>
                <br>

                <input class="form-control" type="date" 
                    value="yyyy-mm-dd" id="d" style=
                    "border:2px solid rgb(0, 128, 28);
                    width:200px;height:30px;">
            </div>
            <br><br><br>

            <div style="display:inline;">dd</div>
            <input class="form-control" type="number" 
                value="1" id="d1" max="31" min="1" size="2" 
                style="border:2px solid rgb(0, 128, 28); 
                width:80px; height:30px;">

            <div style="display: inline;">mm</div>
            <input class="form-control" type="number" 
                value="1" id="m" max="12" min="1" size="2" 
                style="border: 2px solid rgb(0, 128, 28); 
                width:80px; height:30px;">

            <div style="display: inline;">yyyy</div>
            <input class="form-control" type="number" 
                value="2000" id="y" min="2000" max="3000" 
                size="4" maxlength="4"
                style="border:2px solid rgb(0, 128, 28); 
                width:100px;height:30px;">
            <br>

            <div style="text-align: center;">
                <button type="button" class="btn btn-primary 
                    btn-sm" onclick="edit()" style=
                    "background-color: rgb(20, 220, 20);
                    padding:5px;font-family: 'Roboto Slab', serif;">
                    submit
                </button>
            </div>
        </form>
        <br>
    </div>

    <script>
        function edit() {

            // Retrieve the values of  'dd', 'mm', 'yy'
            var dd = document.getElementById("d1").value;
            var mm = document.getElementById("m").value;
            var yy = document.getElementById("y").value;

            // Check if the length of day and month is
            // equal to 1
            if (dd.length == 1) {
                dd = "0" + dd;
            }
            if (mm.length == 1) {
                mm = "0" + mm;
            }

            // Construct a date format like 
            // [yyyy - mm - dd]
            var date = yy + "-" + mm + "-" + dd;

            // Replace the date format with BootStrap
            // date field
            document.getElementById("d").value = date;
        }
    </script>
</body>

</html>
```

**输出:**

![](img/93f4902af40f4a6c30d22ec9e700dd88.png)