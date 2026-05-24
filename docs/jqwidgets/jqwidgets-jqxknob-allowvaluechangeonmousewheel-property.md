# jqxk nob 小部件允许 allowvaluechangeonmousewheel 特性

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jqwidgets-jqxk nob-allowvaluechangeonoussel-property/

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxKnob** 用于表示圆形的 jQuery 插件，并在指定值的范围内显示可拖动的指示器。该应用编程接口也可用于表或矩阵中，以显示指定数据区域中某个值范围内某个字段的相对值。

***allowvaluechangeomousewheel***属性用于设置或获取鼠标滚轮上指定的 **jqxKnob** 的值是否可以更改。

**语法:**

*   用于设置*allowvaluechangeomousewheel*属性。

```html
$('#jqxKnob').jqxKnob({allowValueChangeOnMouseWheel: true });
```

*   获取*allowvaluechangeomousewheel*属性。

```html
var allowValueChangeOnClick = 
$('#jqxKnob').jqxKnob('allowValueChangeOnMouseWheel');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxbuttons . js”>

**示例:**以下示例说明了 jQWidgets**jqxKnob***T5【allowvaluechangeomousewheel*属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="jqwidgets/styles/jqx.base.css" 
          type="text/css"/>
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
            src="jqwidgets/jqxdraw.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxknob.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxnumberinput.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqx-all.js">
    </script>
</head>
<body>
    <center>
        <h1 style="color:green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxKnob 
            allowValueChangeOnMouseWheel Property
        </h3>
        <div id='jqx_Knob'>
            <center>
                GeeksforGeeks
            </center>
        </div>

        <input type="button" style="margin:65px;" 
            id="button_for_allowValueChangeOnMouseWheel"
            value="Value of the allowValueChangeOnMouseWheel property"/>
        <div id="log"></div>

        <script type="text/javascript">
            $(document).ready(function () {
                $('#jqx_Knob').jqxKnob({
                    value: 5,
                    min: 0,
                    max: 50,
                    startAngle: 0,
                    endAngle: 360,
                    snapToStep: true,
                    allowValueChangeOnMouseWheel: true,
                    marks: {
                        colorRemaining: { color: 'red' },
                        colorProgress: { color: 'green' },
                        offset: '70%',
                        thickness: 5,
                        size: '4%'
                    },
                    labels: {
                        offset: '85%',
                        step: 5
                    },
                    progressBar: {
                        style: { fill: 'yellow', 
                                 stroke: 'black' },
                        size: '8%',
                        offset: '61%',
                        background: { fill: 'black' }
                    },
                    pointer: { type: 'arrow', 
                              style: { fill: 'green' }, 
                              size: '68%', 
                              offset: '29%', 
                              thickness: 15 }
                });

                $("#button_for_allowValueChangeOnMouseWheel")
                .jqxButton({
                    width: 350,
                    theme: 'energyblue'
                });

                $('#button_for_allowValueChangeOnMouseWheel')
                .jqxButton().click(function () {
                    var value_of_allowValueChangeOnMouseWheel =
                        $('#jqx_Knob').jqxKnob(
                        'allowValueChangeOnMouseWheel');

                        $("#log").html(
                        value_of_allowValueChangeOnMouseWheel);
                })
            });
        </script>
    </center>
</body>
</html>
```

**输出:**

![](img/a8bff123c3df2c5a7623876e08caab42.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxknob/jquery-knob-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxknob/jquery-knob-api.htm?search=)