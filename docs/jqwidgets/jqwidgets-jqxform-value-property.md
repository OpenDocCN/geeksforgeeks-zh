# jQWidgets jqxForm 值属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxform-value-property/](https://www.geeksforgeeks.org/jqwidgets-jqxform-value-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它非常强大，经过优化，独立于平台，并得到广泛支持。jqxForm 代表一个 jQuery 表单小部件，它包含文本字段、文本区域和密码字段等，帮助我们将数据存储在应用程序的后端。

**值**属性用于设置或返回用于设置 jqxForm 元素值的值属性。它接受一个对象，默认值为{ }。

**语法:**

设置*值*属性。

```html
$('Selector').jqxForm({ value:  object });  
```

返回*值*属性。

```html
var value = $('Selector').jqxForm('value');
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 12 . 4 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-1

**示例:**以下示例说明了 jQWidgets 中的 jqxForm *值*属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
          "jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" 
           src="scripts/jquery-1.12.4.min.js"></script>
    <script type="text/javascript" 
           src="jqwidgets/jqxcore.js"></script>
   <script type="text/javascript" 
           src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
           src="jqwidgets/jqxbuttons.js"></script>
    <script type="text/javascript" 
           src="jqwidgets/jqxinput.js"></script>
    <script type="text/javascript" 
           src="jqwidgets/jqxlistbox.js"></script>
    <script type="text/javascript" 
            src="jqwidgets/jqxscrollbar.js"></script>
    <script type="text/javascript" 
            src="jqwidgets/jqxpanel.js"></script>
    <script type="text/javascript" 
            src="jqwidgets/jqxdropdownlist.js"></script>
    <script type="text/javascript" 
            src="jqwidgets/jqxform.js"></script>
    <script type="text/javascript" 
            src="scripts/demos.js"></script>
</head>

<body>
    <center>
        <h1 style="color:green;">
              GeeksforGeeks
          </h1>

        <h3>jQWidgets jqxForm value property</h3>
        <div id='Form' style="width:400px; height:auto;"></div>  
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            var tp = [
                {
                    bind: 'Name',
                    type: 'text',
                    label: 'Name',
                    required: true,
                    labelWidth: '80px',
                    width: '250px',
                    info: 'Enter Name',
                    infoPosition: 'right'
                }, 
                {
                    bind: 'Email',
                    type: 'text',
                    label: 'Email',
                    required: true,
                    labelWidth: '80px',
                    width: '250px'
                },
                {
                    bind: 'Social',
                    type: 'text',
                    label: 'Social',
                    required: true,
                    labelWidth: '80px',
                    width: '250px'
                },
                {
                    bind: 'Gender',
                    type: 'option',
                    label: 'Gender',
                    required: false,
                    labelWidth: '80px',
                    width: '250px',
                    component: 'jqxDropDownList',
                    options: [
                        { value: 'Male' },
                        { value: 'Female'}
                    ]
                },
                {
                    bind: 'Password',
                    type: 'password',
                    label: 'Password',
                    required: true,
                    labelWidth: '80px',
                    width: '250px'
                },

                {
                    columns: [
                        {
                            type: 'button',
                            text: 'Submit',
                            width: '90px',
                            height: '30px',
                            rowHeight: '40px',
                            columnWidth: '50%',
                            align: 'right'
                        },
                        {
                            type: 'button',
                            text: 'Cancel',
                            width: '90px',
                            height: '30px',
                            rowHeight: '40px',
                            columnWidth: '50%'
                        }                
                    ]
                }
            ];
            var Val = {
                Name: 'ABC',
                Email: 'ABC@gmail.com',
                Social: 'abc',
                Gender: 'Female',
                Password: 'abc',
            };

            $('#Form').jqxForm({
                template: tp,
                value : Val
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/bebaa05e0997352e5071a4dedf964f53.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxform/jquery-form-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxform/jquery-form-api.htm?search=)