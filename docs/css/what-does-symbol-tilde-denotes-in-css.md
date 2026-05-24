# CSS 中的符号颚化符(~)表示什么？

> 原文:[https://www . geeksforgeeks . org/what-do-symbol-tilde-presidents-in-CSS/](https://www.geeksforgeeks.org/what-does-symbol-tilde-denotes-in-css/)

在 CSS 中，符号波浪号(~)被称为**后续兄弟组合符**(也称为波浪号或波浪线或旋转或一般兄弟选择器)。顾名思义，它是由“颚化符”(U+007E，~)字符组成的，用于分隔两个简单选择器序列。由两个序列表示的元素在文档树中共享同一个父元素。它用于选择第一个序列之前的所有第二个序列(不一定是立即的)，或者简单地说，选择指定元素的所有兄弟元素。

**语法:**

```html
first-sequence ~ second-sequence {
    /* property:value; */
}

```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS ~ Selector</title>

    <meta charset="utf-8">
    <meta name="viewport"
        content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <style>
        h1{
            color:green;
            text-align: center;
        }
        hr ~ p {
            text-align: justify;
            background-color: powderblue;
            font-size: 130%;
        }
    </style>
</head>

<body>
    <div class="container">

        <h1>GeeksforGeeks</h1>

        <p>
            Sudo Placement is back to help you this placement
            season. Prepare for the Recruitment drive of 
            product-based companies like Microsoft, Amazon,
            Adobe, etc with our free online placement preparation
            course. The course focuses on various MCQ's & Coding
            question likely to be asked in the interviews & make
            your upcoming placement season efficient and successful.
        </p>

        <hr/>

        <p>
            Sudo Placement is back to help you this placement
            season. Prepare for the Recruitment drive of 
            product-based companies like Microsoft, Amazon,
            Adobe, etc with our free online placement preparation
            course. The course focuses on various MCQ's & Coding
            question likely to be asked in the interviews & make
            your upcoming placement season efficient and successful.
        </p>
    </div>
</body>

</html>
```

**输出:**
![](img/f675949880f6405f844b5b7e325c9898.png)