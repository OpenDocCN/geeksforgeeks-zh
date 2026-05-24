# 如何将 HTML 表单的数据直接发送到 JSON 文件？

> 原文:[https://www . geesforgeks . org/如何将 html 格式的数据直接发送到 json-file/](https://www.geeksforgeeks.org/how-to-send-data-of-html-form-directly-to-json-file/)

任务是将 HTML 形式的数据直接发送到 JSON 文件。

**方法:**我们有一个包含姓名、学院等几个字段的 HTML 表单。我们希望将 HTML 表单的数据直接发送到 JSON 文件。为此，我们使用 *json_encode()* 函数，该函数返回一个 json 编码的字符串。

我们正在制作一个用户在 HTML 表单中填写的值数组。然后我们把这个数组传入 *json_encode()* 函数。然后 *json_encode()* 函数返回一个 json 编码的字符串。整个任务在一个 PHP 函数 *get_data()* 中实现。为了创建一个 JSON 文件，我们使用了 PHP 函数 *file_put_contents()* 。该函数用于将数据写入文件。我们在 *file_put_contents()* 函数中传递 2 个参数。第一个参数是我们的文件名，我们希望在其中以 JSON 格式存储数据，第二个参数是我们的 *get_data()* 函数。

**示例:**下面的 HTML 和 PHP 代码演示了上述方法。

```html
<html>

<head>
    <meta charset="UTF-8">

    <style>
        h3 {
            text-align: center;
        }

        img {
            display: block;
            margin: auto;
            height: 150px;
            width: 150px;
        }

        .input {
            margin: 6px;
            padding: 10px;
            display: block;
            margin: auto;
            color: palevioletred;
            font-size: 30px;
        }

        input {
            width: 90%;
            display: block;
            margin-left: 12px;
            background: none;
            background-color: lightyellow;
        }

        select {
            width: 90%;
            display: block;
            margin-left: 12px;
            background: none;
            background-color: lightyellow;
        }

        #heading {
            font-family: cursive;
            text-align: center;
            color: green;
            padding-top: 20px;

        }

        #form_page {
            height: 500px;
            width: 50%;
            display: flex;
            flex-wrap: wrap;
            flex-direction: row;
            margin: auto;

        }

        #form_body {
            border-radius: 12px;
            height: 330px;
            width: 450px;
            background-color: beige;
            border: 1px solid pink;
            margin: auto;
            margin-top: 12px;
        }

        #text {
            color: red;
            width: 100px;
        }

        #head {
            border-bottom: 2px solid red;
            height: 100px;
            background-color: aliceblue;
        }

        #submit {
            background-color: white;
            width: 70px;
        }
    </style>

</head>

<body>

    <form method="post" action="gfg.php">

        <div id="form_page">

            <div id="form_body">
                <div id="head">
                    <h1 id="heading">GFG</h1>
                </div>
                <br />
                <div id="input_name" class="input">
                    <input id="name" type="text" 
                        Placeholder="Name" name="name" 
                        required>
                </div>
                <div id="input_class" class="input">
                    <input type="text" placeholder=
                        "Branch" name="branch" required>
                </div>
                <div id="input_year" class="input">
                    <input id="school" type="text" 
                        name="college" 
                        placeholder="College">
                </div>

                <div class="id input">
                    <input id="submit" type="submit" 
                        name="submit" value="submit" 
                        onclick="on_submit()">
                </div>
            </div>
        </div>
    </form>

</body>

</html>
```

**gfg.php**这个“gfg.php”文件演示了 HTML 表单内容发布到的 php 代码。

```html
<?php

    if ($_SERVER['REQUEST_METHOD'] == 'POST') {

        function get_data() {
            $datae = array();
            $datae[] = array(
                'Name' => $_POST['name'],
                'Branch' => $_POST['branch'],
                'College' => $_POST['college'],
            );
            return json_encode($datae);
        }

        $name = "gfg";
        $file_name = $name . '.json';

        if(file_put_contents(
            "$file_name", get_data())) {
                echo $file_name .' file created';
            }
        else {
            echo 'There is some error';
        }
    }
?>
```

**输出:**“gfg . json”文件的内容以 JSON 格式显示以下数据。

![](img/3dd3ca9da68b40d3c6e5bc8a6d959eb1.png)

PHP 是一种专门为 web 开发设计的服务器端脚本语言。您可以通过以下 [PHP 教程](https://www.geeksforgeeks.org/php-tutorials/)和 [PHP 示例](https://www.geeksforgeeks.org/php-examples/)从头开始学习 PHP。